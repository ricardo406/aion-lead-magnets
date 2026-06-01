# /meta-ads — Skill de Claude Code (VPS/Linux Install)

Skill para crear y auditar campañas de Meta Ads vía API directamente desde Claude Code. Diseñado para:
- Generar campañas optimizadas (Campaign + Ad Sets + Ads) en estado PAUSED por defecto
- Auditar campañas existentes con tablas de performance, breakdowns y recomendaciones
- Aplicar buenas prácticas de media buyer senior automáticamente

---

## Requisitos en el VPS

- Claude Code instalado (`npm i -g @anthropic-ai/claude-code` o `curl -fsSL https://claude.ai/install.sh | bash`)
- `curl`, `python3` o `node` ya vienen estándar en la mayoría de VPS
- Acceso a una ad account de Meta Business

---

## Instalación rápida vía SSH

### Opción A — Subir el archivo desde tu PC

Desde tu máquina local (donde tienes el zip):

```bash
# 1. Subir el zip al VPS
scp meta-ads-skill-share.zip USER@VPS_IP:~/

# 2. SSH al VPS
ssh USER@VPS_IP

# 3. Dentro del VPS
mkdir -p ~/.claude/skills/meta-ads
unzip ~/meta-ads-skill-share.zip
mv meta-ads-skill-share/SKILL.md ~/.claude/skills/meta-ads/SKILL.md
rm -rf meta-ads-skill-share meta-ads-skill-share.zip
ls -la ~/.claude/skills/meta-ads/SKILL.md  # verificar
```

### Opción B — Crear el archivo directo en el VPS

```bash
mkdir -p ~/.claude/skills/meta-ads
nano ~/.claude/skills/meta-ads/SKILL.md
# Pegar el contenido completo del SKILL.md
# Ctrl+O para guardar, Ctrl+X para salir
```

---

## Configurar `.env` en el proyecto

Cd al directorio donde vas a usar el skill y crea `.env`:

```bash
cd ~/tu-proyecto
cat > .env <<'EOF'
META_AD_ACCOUNT_ID=act_XXXXXXXXXX
META_PAGE_ID=XXXXXXXXXX
META_ACCESS_TOKEN=EAA...

# Opcionales según uso
META_PAGE_ID_WHATSAPP=XXXXXXXXXX
META_PIXEL_ID=XXXXXXXXXX
META_BUSINESS_ID=XXXXXXXXXX
EOF
chmod 600 .env  # Restringe lectura (importante en VPS multi-usuario)
```

### Cómo obtener los IDs

- **Ad Account ID** → Meta Business Suite → Settings → Ad Account. Es el `act_XXXX...`
- **Page ID** → Facebook Page → About → Page ID (al final)
- **Access Token** → https://developers.facebook.com/tools/explorer/
  - Selecciona tu App
  - Permisos mínimos: `ads_management`, `ads_read`, `pages_read_engagement`, `pages_manage_ads`
  - Si vas a WhatsApp: añade `whatsapp_business_management`, `whatsapp_business_messaging`
  - Click "Generate Access Token"

**Importante:** el token del Graph API Explorer caduca cada ~1 hora. Para VPS, genera un **System User Token** desde Business Settings → System Users → Generate New Token (expiration: **Never**). Es el único token viable para producción.

---

## Verificar instalación

```bash
ls -la ~/.claude/skills/meta-ads/SKILL.md
# Debe existir y pesar ~38KB

cd ~/tu-proyecto
claude
# Dentro de Claude Code:
/meta-ads
# Si responde con preguntas sobre la campaña, está bien instalado.
```

---

## Casos de uso

### Crear campaña nueva

```
/meta-ads
```

Claude pregunta: producto, audiencia, presupuesto, landing, objetivo, ángulo, creativo. Genera estructura óptima con 2-3 ad sets y 2-3 variaciones de copy por ad set.

### Auditar campaña existente

```
/meta-ads
Quiero auditar la campaña [ID o nombre]
```

Claude pull data de la API, analiza performance ad-by-ad, identifica winners/losers, hace recomendaciones específicas con copy nuevo si aplica.

### Optimizar campaña activa

Después de auditar, Claude puede aplicar cambios vía API (todos en estado PAUSED por seguridad, con confirmación explícita antes de tocar nada).

---

## Reglas duras del skill

- Todas las campañas se crean en **PAUSED** por defecto
- **Máximo $50/día** por defecto (refusable solo con instrucción explícita)
- Cero copy duplicado entre ads — siempre 3 ángulos distintos (Pain / Transformation / Urgency)
- Spanish neutro (`tú`, sin voseo ni mexicanismos) salvo que pidas otro idioma
- Naming convention profesional automática para campaigns, adsets, ads y creatives
- Validación de compliance (categoría especial, claims, atributos personales)
- Dry-run obligatorio antes de cualquier `POST` a Meta API

---

## Troubleshooting

- **Error 190 (token expired)** → regenera el token. Para VPS, usa System User Token (`expires: never`).
- **Error 1885183 (app in development)** → publica tu app en developers.facebook.com → App Review → Publish.
- **Error 2923012 (WhatsApp Business required)** → tu System User necesita scope `whatsapp_business_management`.
- **Error 1815694 (permissions)** → tu System User no está asignado a la ad account. Ve a Business Settings → Users → System Users → tu user → Add Assets → Ad Accounts.
- **Error 1359202 (Cannot Disable Advantage Options)** → si activas Advantage+ Audience, no puedes setear placements manuales. O Advantage+ ON con placements auto, o Advantage+ OFF con placements manuales.

---

## Tips para VPS

- **Persistir env vars:** si vas a correr Claude Code en background o vía script, exporta las vars en `~/.bashrc` o usa `set -a; source .env; set +a` antes de invocar.
- **Token rotation:** Meta puede invalidar tokens si detecta uso sospechoso. Mantén tu System User Token guardado en un password manager.
- **Cron / automation:** si quieres correr auditorías automáticas con Claude Code en cron, asegúrate que el cron job tenga acceso a `~/.claude/` y al `.env`.
- **Multi-tenant:** si manejas varias cuentas (ej. cliente A y cliente B), crea folders separados con su propio `.env` cada uno.

---

## Estructura del archivo

`SKILL.md` está optimizado para Claude Code. No necesitas leerlo manualmente — Claude lo carga y sigue las reglas internas.

---

Si tienes problemas con la instalación o el uso, contacta a Ricardo.
