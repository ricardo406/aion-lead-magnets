---
name: meta-ads
description: Crea campañas optimizadas en Meta Ads con estructura estratégica (múltiples ad sets y ads para A/B testing). Úsalo cuando el usuario diga /meta-ads o quiera crear anuncios, campañas, o ads en Facebook/Instagram.
disable-model-invocation: true
argument-hint: <producto o servicio a anunciar>
---

<!-- AION-POTENCIADO-v1 -->

# Potenciación AION — reglas obligatorias

## Contrato de ejecución Ricardo/AION

- Escribe siempre en español neutro, directo, usando "tú". Prohibido usar "vos", "tenés", "querés", "sos" o mexicanismos como "te late", "qué padre", "chido", "órale".
- Estilo: claro, agresivo en precisión, orientado a negocio, tipo Hormozi/Gadzhi, sin relleno motivacional ni frases genéricas.
- La audiencia principal son dueños hispanos de servicios locales, ecommerce y B2B que quieren más leads, seguimiento, ventas y automatización con agentes IA + Meta Ads.
- Nunca inventes datos críticos: presupuesto, credenciales, IDs, ubicación, claims, resultados, fechas, nombres de cliente, permisos o rutas.
- Si falta un input requerido, detente y pide solo ese dato. No hagas 10 preguntas si una bloquea la ejecución.
- Entrega output listo para usar. Nada de "borrador", "ejemplo genérico" o "ajústalo tú" cuando el skill puede producir el entregable final.

## Preflight obligatorio antes de ejecutar

Antes de crear, renderizar, publicar, duplicar, subir, descargar o llamar APIs externas, valida:

1. Inputs requeridos presentes y coherentes.
2. Rutas de entrada/salida existen o pueden crearse.
3. Credenciales/env vars necesarias están disponibles.
4. Herramientas externas requeridas están activas y en versión usable.
5. El formato final esperado está definido: PDF, PNG, MP4, JSON, campaña PAUSED, workflow n8n, etc.
6. Riesgo de side effects: publicación, gasto publicitario, duplicación de workflows, subida de assets, descarga externa.

Si hay side effects irreversibles o externos, muestra un resumen corto y pide confirmación explícita antes de ejecutar.

## Manifest por ejecución

Crea o actualiza un manifest junto al output cuando aplique:

- skill
- fecha
- inputs críticos
- rutas de entrada
- carpeta de salida
- herramientas usadas
- assets generados/descargados
- IDs externos creados/modificados
- decisiones tomadas
- fallbacks usados
- hash o tamaño de archivos finales
- estado: planificado | generado | revisado | publicado | fallido

## Manejo de errores

- Si falla una API: reintenta una vez si es seguro; si vuelve a fallar, usa fallback local o detente con error claro.
- Si falla un render: guarda logs, captura el frame/asset problemático y no declares éxito.
- Si falla una publicación o creación externa: reporta estado exacto, IDs parciales y siguiente acción segura.
- Si una dependencia cambió versión/permisos: no improvises; pide actualización de credenciales o confirma nuevo flujo.

## QA final obligatorio

Antes de responder "terminado", verifica:

- Archivo final existe en la ruta esperada.
- Formato y dimensiones correctas.
- Tono Ricardo/AION correcto: tú, directo, español neutro, sin mexicanismos ni voseo.
- CTA claro y alineado con AION.
- No hay placeholders, TODOs visibles, claims inventados ni texto genérico.
- Si hubo API/side effect, el estado final y los IDs quedan registrados.



## Upgrade específico /meta-ads

### Preflight media buyer

Antes de crear nada valida: META_ACCESS_TOKEN, META_AD_ACCOUNT_ID, META_PAGE_ID, objetivo, presupuesto, oferta, vertical, audiencia, pixel/evento si aplica, ubicación y naming convention.

### Seguridad de gasto

Toda campaña debe quedar PAUSED por defecto. Respeta máximo $50/día salvo instrucción explícita. Pide confirmación antes de llamar la Marketing API para crear campañas, ad sets o ads.

### Matriz de ángulos AION

Genera variaciones por ángulo: leads perdidos, seguimiento lento, agenda vacía, automatización n8n/GHL, Meta Ads rentable, velocidad de respuesta y oferta irresistible.

<!-- /AION-POTENCIADO-v1 -->

<!-- META-ADS-MAX-v2 -->

# Upgrade Máximo — /meta-ads como media buyer senior AION

## Principio rector

Este skill no debe limitarse a “crear campañas”. Debe operar como media buyer senior responsable: estrategia, compliance, estructura, copy, assets, validación técnica, dry-run, creación segura en PAUSED, manifest y rollback. Cada decisión debe proteger presupuesto, reducir rechazo de anuncios y aumentar probabilidad de leads/citas reales para AION o clientes AION.

Regla central: no se toca Meta Marketing API hasta que estrategia, compliance, presupuesto, assets, tracking y confirmación estén cerrados.

## Contrato de seguridad publicitaria

- Todas las campañas, ad sets y ads se crean PAUSED por defecto.
- Presupuesto máximo por defecto: $50/día total, salvo instrucción explícita del usuario.
- Nunca activar campañas. Solo crear/editar en estado PAUSED, excepto si el usuario pide activación explícita y confirma riesgo.
- Nunca imprimir META_ACCESS_TOKEN completo ni credenciales completas en logs/reportes.
- Nunca inventar pixel, evento, página, audiencia, ubicación, presupuesto, oferta o claims.
- Si el usuario pide algo que puede violar políticas Meta, proponer versión compliant antes de crear.
- Si falta un dato bloqueante, pedir solo ese dato y detener ejecución.

## Intake mínimo obligatorio

Antes de diseñar campaña, confirmar o inferir de forma explícita:

1. Cliente/negocio.
2. Vertical: servicios locales, ecommerce, B2B, coaching, restaurantes, real estate o default.
3. Oferta concreta.
4. Objetivo: leads, mensajes, ventas, tráfico, awareness, llamadas, reservas, formularios.
5. Ubicación/geografía.
6. Presupuesto diario total.
7. Página/Instagram/Facebook que se usará.
8. Asset creativo disponible o necesidad de generar/subir imagen/video.
9. Destino del lead: WhatsApp, Instant Form, landing, GHL, calendario, llamada, DM.
10. Pixel/evento si aplica.
11. Restricciones de compliance del nicho.
12. Fecha/naming del lanzamiento.

Inputs bloqueantes para API create: META_ACCESS_TOKEN, META_AD_ACCOUNT_ID, META_PAGE_ID, objetivo, presupuesto, geo, oferta, destino del lead y confirmación explícita.

## Decisión estratégica antes de estructura

Primero decide el tipo correcto de campaña. No uses una plantilla fija si el objetivo pide otra cosa.

### Servicios locales

- Si quiere citas/reservas rápido: Leads o Messages según destino operativo.
- Si GHL/calendario está listo: Leads con Instant Form o landing + seguimiento GHL.
- Si WhatsApp es canal principal: Click-to-WhatsApp/Messages con copy de respuesta rápida.

### Ecommerce

- Si hay pixel y catálogo: Sales/conversions.
- Si no hay pixel confiable: tráfico cualificado o mensajes con oferta concreta, pero explicar limitación.
- Separar prospecting vs retargeting si hay data suficiente.

### B2B

- Lead Gen o landing con formulario de alta intención.
- Copy orientado a dolor operativo, costo de oportunidad, velocidad de seguimiento y pipeline.
- Evitar promesas exageradas de ingresos.

## Arquitectura de campaña recomendada

Por defecto, diseñar:

- 1 campaña por objetivo/oferta.
- 2-3 ad sets con hipótesis diferentes, no duplicados disfrazados.
- 2-3 ads por ad set con ángulos distintos.
- Status PAUSED en todos los niveles.
- Naming consistente.

Ad set hypotheses:

1. Broad/Advantage+ si aplica y el mercado es amplio.
2. Intereses/intención por vertical.
3. Retarget/lookalike solo si hay fuente real y suficiente data.

No crear más estructura de la necesaria. Más campañas no significa más performance.

## Matriz de ángulos AION

Genera copy desde ángulos de negocio, no desde frases genéricas.

### Servicios locales

- Leads perdidos: “Si tardas 2 horas en responder, ese cliente ya habló con otro.”
- Agenda vacía: automatización para convertir consultas en citas.
- Seguimiento: GHL/n8n respondiendo, calificando y agendando.
- Prueba operativa: menos caos, más control del pipeline.

### Ecommerce

- Carritos abandonados.
- Recompra y retención.
- Atención automática por WhatsApp/DM.
- Oferta clara + urgencia real, sin falsa escasez.

### B2B

- Pipeline lento.
- Leads sin seguimiento.
- Demos que no se agendan.
- Coste de oportunidad del equipo comercial.

### AION core

- Agentes IA que responden en segundos.
- n8n + GoHighLevel como sistema, no “chatbot”.
- Meta Ads que alimentan un pipeline automatizado.
- Oferta + seguimiento + citas, no solo clicks.

## Copywriting rules

- Español neutro, directo, con “tú”.
- Sin mexicanismos, sin voseo, sin promesas garantizadas.
- Primary text: abrir con dolor o oportunidad concreta.
- Headline: resultado/beneficio específico sin exagerar.
- Description: mecanismo o CTA claro.
- CTA alineado al destino: Send Message, Learn More, Sign Up, Book Now, Contact Us.
- Evitar “revoluciona”, “transforma tu negocio” y frases vacías si no están aterrizadas.

## Meta Ads Compliance Gate obligatorio

Antes de crear cualquier Campaign, Ad Set, Ad Creative o Ad, valida y registra en el dry-run:

1. Categoría especial: crédito, empleo, vivienda, política/social. Si aplica, detener y pedir configuración exacta.
2. Atributos personales: prohibido copy tipo “¿Eres dueño endeudado?”, “¿Tienes problemas financieros?”, “¿Estás enfermo?”.
3. Claims de resultados: prohibido garantizar leads, ventas, ingresos, ROAS o citas.
4. Before/after: evitar claims visuales o textuales agresivos de transformación garantizada.
5. Salud/finanzas/legal: usar lenguaje cuidadoso y no diagnóstico.
6. Landing/destino: promesa del anuncio debe coincidir con la página/formulario/WhatsApp.
7. Política de privacidad: necesaria para formularios/landing si se capturan datos.
8. Creativo: sin texto engañoso, sin logos no autorizados, sin capturas privadas sensibles.
9. Rechazo probable: si hay riesgo, reescribir copy en versión compliant antes de API create.

Si el Compliance Gate falla, no crear. Entregar “Bloqueado por compliance” + versión corregida.

## Tracking y evento

Antes de definir optimization_goal, validar:

- ¿El lead ocurre en Instant Form, WhatsApp, landing, GHL/calendario o ecommerce?
- Si usa landing: pixel existe y evento correcto está configurado.
- Si no hay pixel/evento confiable: explicar limitación y elegir objetivo más seguro.
- Si usa GHL: confirmar location/form/calendar y seguimiento.
- No fingir conversion optimization si no hay señal real.

## Creative specs y asset QA

Validar cada asset antes de crear ad creative:

- Formato: imagen/video compatible con Meta.
- Ratio: 1:1, 4:5 o 9:16 según placement.
- Resolución suficiente, sin pixelación.
- Texto legible móvil.
- Oferta visible o mecanismo claro.
- Marca/página coherente.
- Sin claims visuales dudosos.
- Nombre de archivo limpio.

Para AION, priorizar creatives que muestren mecanismo: pipeline, WhatsApp, GHL, citas, automatización, antes/después operativo sobrio, no stock genérico.

## Naming convention obligatorio

Usa esta convención salvo instrucción distinta:

Campaign:
`AION_{cliente}_{vertical}_{objetivo}_{oferta}_{geo}_{YYYYMMDD}`

Ad Set:
`AS_{audiencia}_{geo}_{placement}_{budget}`

Ad:
`AD_{angle}_{creative}_{variant}`

Ejemplo:
`AION_DentalPlus_servicioslocales_leads_implantes_miami_20260503`

## Dry-run obligatorio antes de API create

Antes de llamar Meta Marketing API, mostrar una tabla con:

### Campaign

- name
- objective
- buying_type
- status=PAUSED
- special_ad_categories
- daily budget total

### Ad Sets

- name
- audience hypothesis
- geo
- age/gender si aplica
- placements
- optimization_goal
- billing_event
- budget
- pixel/event o destino

### Ads

- name
- angle
- primary text
- headline
- description
- CTA
- creative asset
- compliance status

### Riesgos

- compliance
- tracking
- presupuesto
- assets
- permisos/API
- datos faltantes

No crear nada hasta recibir confirmación textual explícita:

`CONFIRMO CREAR PAUSADO`

Cualquier otra respuesta se trata como no confirmado.

## Payload sanitizado

Antes de API create, construir payloads de campaña/adsets/ads pero mostrarlos sanitizados:

- No mostrar access token.
- Redactar IDs sensibles si el usuario no necesita verlos completos.
- Mostrar status PAUSED.
- Mostrar budget en unidades humanas y, si aplica, en minor units para API.
- Mostrar objective/optimization_goal/CTA exactos.

## Orden seguro de creación

Crear en este orden:

1. Validar credenciales/permisos.
2. Subir/validar creative asset si aplica.
3. Crear Campaign PAUSED.
4. Crear Ad Sets PAUSED.
5. Crear Ad Creatives.
6. Crear Ads PAUSED.
7. Verificar por lectura API que todo quedó PAUSED.
8. Guardar manifest.
9. Reportar IDs y próximos pasos.

Si falla cualquier paso después de crear IDs, no reintentar a ciegas. Consultar estado y registrar parcial.

## Manifest y rollback

Guardar `meta-ads-manifest.json` en la carpeta del cliente/campaña con:

- fecha
- skill=/meta-ads
- cliente
- oferta
- objective
- budget
- account_id
- page_id
- campaign_id
- adset_ids
- adcreative_ids
- ad_ids
- status verificado
- payloads sanitizados
- asset paths/hashes
- compliance result
- dry-run aprobado por usuario
- errores parciales
- rollback plan

Rollback seguro:

- Si algo queda creado por error, pausar todo lo creado.
- No borrar campañas automáticamente salvo instrucción explícita.
- Reportar IDs para revisión manual en Ads Manager.

## Post-create QA

Después de crear, verificar:

- Campaign existe y está PAUSED.
- Todos los Ad Sets están PAUSED.
- Todos los Ads están PAUSED.
- Presupuesto no excede lo confirmado.
- Objective/optimization_goal coinciden con dry-run.
- Página correcta.
- Creatives asociados correctamente.
- Manifest guardado.

No decir “terminado” si no se verificó estado por API o si no se puede verificar.

## Manejo de errores Meta API

Errores comunes y respuesta:

- Token vencido: detener, pedir renovar META_ACCESS_TOKEN.
- Permisos insuficientes: reportar permiso faltante y no reintentar.
- Ad account inválido: verificar META_AD_ACCOUNT_ID.
- Page ID sin acceso: pedir página correcta/permisos.
- Creative rechazado: crear versión compliant, no insistir igual.
- Pixel/event faltante: cambiar objetivo o pedir configuración.
- Rate limit: esperar/reintentar una vez si es seguro.
- Error parcial: consultar IDs creados, pausar lo creado y guardar manifest parcial.

## Output final obligatorio

El reporte final debe incluir:

- Qué se creó.
- Qué NO se creó.
- Estado PAUSED verificado.
- Presupuesto final.
- IDs creados.
- Ruta del manifest.
- Riesgos/compliance.
- Próximos pasos recomendados antes de activar.

## Anti-patrones prohibidos

- Crear campañas sin dry-run.
- Crear campañas ACTIVE por defecto.
- Superar $50/día sin permiso.
- Usar claims de ingresos garantizados.
- Usar “chatbot” cuando se vende sistema/agente IA AION, salvo contexto específico.
- Copys genéricos tipo “lleva tu negocio al siguiente nivel”.
- Audiencias duplicadas sin hipótesis.
- Ignorar pixel/evento.
- No guardar IDs.
- Decir que se creó todo sin verificar estado.

## Checklist final de nivel máximo

- [ ] Intake completo.
- [ ] Compliance Gate aprobado.
- [ ] Tracking/destino validado.
- [ ] Assets validados.
- [ ] Estructura con hipótesis claras.
- [ ] Copy AION directo y compliant.
- [ ] Dry-run mostrado.
- [ ] Confirmación exacta recibida.
- [ ] Todo creado PAUSED.
- [ ] Estado verificado por API.
- [ ] Manifest guardado.
- [ ] Reporte final claro.

<!-- /META-ADS-MAX-v2 -->

## What This Skill Does

Creates optimized Meta Ads campaigns via the Marketing API. Acts as an expert media buyer: analyzes the product and audience, designs the optimal campaign structure (multiple ad sets with different targeting, multiple ad variations per ad set), generates all ad copy, and creates everything via API calls.

**Every campaign is strategically structured for maximum performance.** Claude decides the ideal number of ad sets, targeting variations, and ad copy variations based on the budget and audience.

---

## Setup — Environment Variables (.env)

Before using this skill, the user MUST have a `.env` file in the project root with these variables:

```env
# Meta Ads API (REQUIRED)
META_AD_ACCOUNT_ID=act_XXXXXXXXXX
META_PAGE_ID=XXXXXXXXXX
META_ACCESS_TOKEN=XXXXXXXXXX

# Optional — only needed for specific features
META_PAGE_ID_WHATSAPP=XXXXXXXXXX   # Only if running Click-to-WhatsApp campaigns
META_PIXEL_ID=XXXXXXXXXX           # Only if running Purchase/conversion campaigns
META_BUSINESS_ID=XXXXXXXXXX        # Only if managing business-level assets
```

**On startup, ALWAYS load the .env file first:**
```bash
set -a && source .env && set +a
```

If the `.env` file doesn't exist or is missing required variables (`META_AD_ACCOUNT_ID`, `META_PAGE_ID`, `META_ACCESS_TOKEN`), guide the user to create it:
1. **Ad Account ID** → Meta Business Suite > Settings > Ad Account > Copy the `act_XXXX` ID
2. **Page ID** → Facebook Page > About > Page ID
3. **Access Token** → developers.facebook.com > Graph API Explorer > Select your app > Generate Token (with `ads_management`, `pages_read_engagement` permissions)

**IMPORTANT:** The token from Graph API Explorer expires every ~1 hour. If you get an expired token error, ask the user to regenerate. For a permanent token, guide them to create a **System User Token** from Business Manager > Business Settings > System Users.

**IMPORTANT:** For WhatsApp destination ads, the token MUST include `whatsapp_business_management` and `whatsapp_business_messaging` permissions. Without these, the API will error with "Page With WhatsApp Business Account Required" even if the page has WhatsApp Business connected. Always remind users to add these permissions in Graph API Explorer when generating tokens for WhatsApp campaigns.

**IMPORTANT:** WhatsApp destination ads can ONLY be modified from Ads Manager UI, not via API with user tokens. If the user wants Click-to-WhatsApp, create the structure via API and tell them to set the WhatsApp destination in Ads Manager, OR use Messenger destination which works via API.

---

## Professional Naming Convention

ALL campaigns, ad sets, ads, and creatives MUST follow this naming convention:

### Campaign Name Format
```
[Brand] | [Objective] — [Destination] | [Funnel Stage] [Type] | [Date]
```
Examples:
- `AION Growth Lab | Sales — Purchase | BOF Retargeting | 03.30.26`
- `AION Growth Lab | Engagement — WhatsApp | TOF Prospecting | 03.17.26`
- `AION Growth Lab | Traffic — Skool | MOF Nurture | 04.01.26`

### Ad Set Name Format
```
[Funnel Stage] | [Audience Description] | [Optimization] | [Placement Note]
```
Examples:
- `BOF | Warm Retargeting | Web Visitors + IG Engagers + Video Viewers | Purchase Opt.`
- `TOF | Broad 25-65 US | Hispanos | WhatsApp Conversations | Advantage+`
- `MOF | Lookalike 1% Purchasers | Link Clicks | All Placements`

### Ad Name Format
```
[Format] | [Angle] — "[Hook Quote]" | [Version]
```
Examples:
- `UGC Video | Pain Point — "Generá Clientes Con IA" | v1 (Winner)`
- `Static | FOMO — "Tu Competencia Ya Está Adentro" | v2`
- `Carousel | Social Proof — "Resultados Reales" | v3`

### Creative Name Format
```
[Funnel Code] | [Angle] — "[Hook Quote]" | [Version]
```
Examples:
- `RTG | Direct CTA — "Ya Viste De Qué Se Trata" | v1`
- `MSG | Urgency — "Dejando Dinero Sobre La Mesa" | v3`

### Funnel Stage Codes
- **TOF** = Top of Funnel (prospecting, cold audiences)
- **MOF** = Middle of Funnel (engagement, video viewers, IG engagers)
- **BOF** = Bottom of Funnel (retargeting, website visitors, warm leads)
- **RTG** = Retargeting creative
- **MSG** = Messenger creative

---

## Existing Custom Audiences

Before creating new audiences, query what already exists in the user's account:

```bash
curl -s "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/customaudiences?fields=id,name,subtype,approximate_count&access_token=${META_ACCESS_TOKEN}" | python3 -c "import sys,json; data=json.load(sys.stdin); [print(f'{a[\"name\"]:40s} | {a[\"id\"]:20s} | {a.get(\"subtype\",\"N/A\"):15s} | ~{a.get(\"approximate_count\",0):,}') for a in data.get('data',[])]"
```

Show the results to the user so they can choose which audiences to use for retargeting.

---

## Copy Framework — Professional Copywriting Rules

### The 3 Angles (ALWAYS use different angles per ad, NEVER duplicate copy)

**Angle A — Pain Point ("El Dolor")**
- Lead with the problem the audience faces RIGHT NOW
- Make them feel the cost of inaction
- Transition to the solution
- Structure: Problem → Agitation → Solution → CTA

**Angle B — Transformation ("La Transformación")**
- Paint the "after" picture — what life looks like with the product
- Use "Imagina..." or "→" arrows to list benefits
- Contrast with current state
- Structure: Vision → What You Get → Proof → CTA

**Angle C — Urgency / Social Proof ("La Urgencia")**
- Real urgency (cost of waiting), NOT fake scarcity
- Reference what others are already doing
- Create FOMO through results, not countdown timers
- Structure: What others are doing → What you're missing → What's inside → CTA

### Copy Quality Rules
- **NEVER** duplicate copy between ads — each ad MUST have a unique angle
- **NEVER** use generic copy like "Únete a nuestra comunidad y accede a entrenamientos en vivo" — be SPECIFIC
- **NEVER** have grammatical errors — double-check accents (enseñar, estás, detrás, más)
- **ALWAYS** use proper Spanish: "si no" (separado), proper accents, proper punctuation
- **ALWAYS** end with a clear, direct CTA (not passive)
- **ALWAYS** vary headlines between ads — identical headlines = zero testing value
- **NEVER** lead with price in ALL headlines — test value-first vs price-first
- Use emojis strategically (✅, 🔥, →, 👇) but don't overdo it
- Primary text should be 100-200 words — long enough to sell, short enough to hold attention
- First line is EVERYTHING — it must stop the scroll

### Retargeting Copy Rules (BOF)
- The person already KNOWS you — don't re-introduce yourself
- Address the specific reason they didn't buy
- Be direct: "Ya viste de qué se trata. Solo falta que entres."
- Use shorter copy (80-120 words) — they don't need education, they need a push
- Acknowledge their return: "Volviste a verlo. Eso significa que sabes que lo necesitas."

---

## Campaign Architecture Best Practices

### Budget Strategy
- **CBO (Campaign Budget Optimization)** is preferred — let Meta distribute
- Set budget at campaign level with `daily_budget` in cents
- Do NOT set individual ad set budgets when using CBO
- For retargeting: $10-15/day is enough (small audiences)
- For prospecting: $25-50/day minimum for meaningful data

### Funnel Architecture
```
TOF (Prospecting) — $30-40/day
├── Broad audience, multiple video/UGC ads
├── Optimize for: Conversations (WhatsApp/Messenger) or Link Clicks
└── Goal: Fill the funnel with warm leads

MOF (Nurture) — $10-15/day
├── Video viewers 50%+, IG engagers
├── Optimize for: Link Clicks or Conversations
└── Goal: Deepen engagement, build trust

BOF (Retargeting) — $10-15/day
├── Web visitors, Video viewers 75%+, messaging contacts
├── Optimize for: Purchase (OFFSITE_CONVERSIONS)
└── Goal: Close the sale
```

### Retargeting Strategy (BOF)
- Combine warm audiences: Website visitors + IG Interaction + Video viewers
- Use `custom_audiences` in targeting with audience IDs
- Set `targeting_automation.advantage_audience: 0` to keep strict retargeting
- Include Pixel with `promoted_object.custom_event_type: "PURCHASE"`
- Frequency cap: watch for >3 frequency — rotate creatives if exceeded

### Advantage+ Audience Rules
- When using `advantage_audience: 1`, `age_max` MUST be 65 (Meta requirement)
- Use suggestions for age, not hard limits
- Works best for TOF prospecting

### Optimization Goals by Objective
| Objective | optimization_goal | promoted_object |
|-----------|-------------------|-----------------|
| OUTCOME_SALES | OFFSITE_CONVERSIONS | `{pixel_id, custom_event_type: "PURCHASE"}` |
| OUTCOME_TRAFFIC | LINK_CLICKS | `{page_id}` |
| OUTCOME_ENGAGEMENT + Messenger | CONVERSATIONS | `{page_id}` + `destination_type: "MESSENGER"` |
| OUTCOME_ENGAGEMENT + WhatsApp | CONVERSATIONS | `{page_id}` + `destination_type: "WHATSAPP"` (requires WA Business) |
| OUTCOME_LEADS | LEAD_GENERATION | `{page_id}` |

---

## Auditing Existing Campaigns — Protocolo de Máximo Nivel

### Principio

Una auditoría real no describe lo que Meta Ads Manager ya muestra. Extrae las dimensiones que la UI oculta o no combina, las analiza juntas, y entrega decisiones específicas: qué pausar, qué escalar, qué testear, y por qué exactamente.

### Paso 1: Estructura base

Siempre comenzar por esto antes de ir a números:

```bash
# Todas las campañas con estado y presupuesto
curl -s "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/campaigns?fields=id,name,status,objective,daily_budget,lifetime_budget,buying_type,special_ad_categories&limit=50&access_token=${META_ACCESS_TOKEN}"

# Ad sets de cada campaña activa
curl -s "https://graph.facebook.com/v22.0/{CAMPAIGN_ID}/adsets?fields=id,name,status,optimization_goal,billing_event,daily_budget,targeting,destination_type,promoted_object&access_token=${META_ACCESS_TOKEN}"

# Ads de cada ad set activo
curl -s "https://graph.facebook.com/v22.0/{ADSET_ID}/ads?fields=id,name,status&access_token=${META_ACCESS_TOKEN}"
```

### Paso 2: Performance por ad — nivel base

```bash
# Insights a nivel de ad, período máximo
curl -s "https://graph.facebook.com/v22.0/{CAMPAIGN_ID}/insights?level=ad&date_preset=maximum&fields=ad_id,ad_name,adset_name,spend,impressions,reach,frequency,clicks,ctr,cpm,actions,cost_per_action_type,video_thruplay_watched_actions,video_avg_time_watched_actions,video_p25_watched_actions,video_p50_watched_actions,video_p75_watched_actions,video_p100_watched_actions,inline_link_clicks,inline_link_click_ctr,website_ctr,outbound_clicks,outbound_clicks_ctr,landing_page_views,quality_ranking,engagement_rate_ranking,conversion_rate_ranking&access_token=${META_ACCESS_TOKEN}"
```

**Métricas clave a extraer por ad:**
- Spend + % del total (identificar winners y zombies)
- Frecuencia (>2.5 en BOF = fatiga inminente, >3 = urgente rotar)
- **Hook rate** = `video_p25_watched / impressions` — si <25% el primer segundo no engancha
- **Hold rate** = `video_p75_watched / video_p25_watched` — si <40% el contenido pierde atención
- **Link CTR** (inline_link_click_ctr) vs **All CTR** (ctr) — diferencia alta = clicks de perfil/logo, no del destino
- **LPV rate** = `landing_page_views / outbound_clicks` — si <55% hay problema de carga o desconfianza
- **Cost per LPV** vs **CPC** — si difieren >40%, hay pérdida en tránsito
- **quality_ranking** / **engagement_rate_ranking** / **conversion_rate_ranking** — below_average = Meta degrada el alcance y sube el CPM hasta 3x
- Resultado primario (conversiones, mensajes, compras) + CPR (costo por resultado)
- **Ads muertos:** <1% del gasto total después de 5+ días activos → pausar

### Paso 3: Breakdown Edad × Género

```bash
curl -s "https://graph.facebook.com/v22.0/{CAMPAIGN_ID}/insights?date_preset=maximum&breakdowns=age,gender&fields=spend,impressions,ctr,cpm,frequency,actions,cost_per_action_type&access_token=${META_ACCESS_TOKEN}"
```

**Qué buscar:**
- ¿Qué segmento tiene el CPR más bajo? → Candidato a excluir o escalar según resultado
- ¿Hay segmentos con >20% del spend y 0 conversiones? → Excluir por edad/sexo
- ¿Mujeres vs hombres convierten diferente? → Puede justificar ad sets separados con copy específico
- ¿El segmento que más gasta es el que mejor convierte? → Si no, hay un error de entrega de Meta o de targeting

### Paso 4: Breakdown Plataforma × Placement

```bash
curl -s "https://graph.facebook.com/v22.0/{CAMPAIGN_ID}/insights?date_preset=maximum&breakdowns=publisher_platform,platform_position&fields=spend,impressions,ctr,cpm,frequency,actions,cost_per_action_type&access_token=${META_ACCESS_TOKEN}"
```

**Qué buscar:**
- ¿Qué placement tiene el CPR más bajo? → Considerar crear ad set exclusivo para ese placement con creativo nativo (9:16 para Reels/Stories, 1:1 para Feed)
- ¿Audience Network está recibiendo gasto? → Casi siempre se debe excluir en campañas de conversión (tráfico de baja calidad)
- ¿Instagram vs Facebook convierten diferente? → Si diferencia >40% en CPR, separar en ad sets distintos
- ¿Los Reels tienen buen CTR pero mal CPR? → El creativo engancha pero no convence; problema de oferta o destino

### Paso 5: Breakdown Dispositivo (iOS vs Android vs Desktop)

```bash
curl -s "https://graph.facebook.com/v22.0/{CAMPAIGN_ID}/insights?date_preset=maximum&breakdowns=impression_device&fields=spend,impressions,ctr,cpm,frequency,actions,cost_per_action_type&access_token=${META_ACCESS_TOKEN}"
```

**Dispositivos que devuelve Meta:** `iphone`, `ipad`, `android_smartphone`, `android_tablet`, `desktop`

**Qué buscar:**
- **iOS vs Android en conversiones:** iOS 14+ degradó el pixel de Meta — si ves muchas conversiones en Android y pocas en iOS pero gasto similar, es probable subatribución en iOS, no que iOS no convierta. El CPR real de iPhone puede ser mejor de lo que parece.
- **Desktop recibiendo gasto con 0 conversiones:** Si el destino es WhatsApp o una landing mobile-first, desktop no convierte. Excluir dispositivo en targeting si aplica.
- **Distribución de gasto:** Si iPhone recibe 60% del gasto pero los datos de conversión son escasos (por ATT), Meta puede estar sobreinvirtiendo en un segmento sin señal de retorno. Evaluar si tiene sentido ajustar bid por dispositivo.
- **Android con CPR bajo y iOS sin datos claros:** Considera crear un ad set device-specific para Android donde la señal del pixel es más limpia.

### Paso 6: Breakdown Región (Estado)

```bash
curl -s "https://graph.facebook.com/v22.0/{CAMPAIGN_ID}/insights?date_preset=maximum&breakdowns=region&fields=spend,impressions,ctr,cpm,actions,cost_per_action_type&access_token=${META_ACCESS_TOKEN}"
```

**Qué buscar:**
- ¿Un estado recibe >35% del gasto total? → Concentración de riesgo. Cualquier evento en ese estado (elecciones, restricciones, estacionalidad) colapsa la campaña.
- ¿Hay estados con alto spend y 0 conversiones? → Añadir a geo exclusions o reducir entrega
- ¿Los estados con conversiones son los mismos donde está la audiencia objetivo? → Si no, hay un problema de targeting o de creative relevance para ese mercado
- Comparar CPR por estado: si Florida convierte a $15 y California a $60 con el mismo ad, segmentar en ad sets geo-específicos puede reducir CPR promedio

### Paso 7: Breakdown Hora del Día

```bash
curl -s "https://graph.facebook.com/v22.0/{CAMPAIGN_ID}/insights?date_preset=maximum&breakdowns=hourly_stats_aggregated_by_advertiser_time_zone&fields=spend,impressions,ctr,cpm,actions,cost_per_action_type&access_token=${META_ACCESS_TOKEN}"
```

**Qué buscar:**
- ¿En qué horas se producen el 70%+ de las conversiones? → Si es 7-10pm y estás pagando a precio plano las 24h, el ad schedule reduce CPR considerablemente
- ¿Las horas de mayor spend coinciden con las horas de mayor conversión? → Si no, hay ineficiencia de presupuesto
- ¿Horas de alta impresión con CTR bajo (ej. 2-5am)? → Meta puede estar quemando impresiones baratas pero inútiles en horario de baja intención
- **Regla práctica:** Si una ventana de 6 horas genera <5% de las conversiones pero >15% del spend, implementar ad schedule excluyendo esas horas

### Paso 8: Attribution Window

```bash
# Comparar 1-day click vs 7-day click vs 1-day view
curl -s "https://graph.facebook.com/v22.0/{CAMPAIGN_ID}/insights?date_preset=maximum&level=ad&action_attribution_windows=['1d_click','7d_click','1d_view']&fields=ad_id,ad_name,spend,actions,cost_per_action_type&access_token=${META_ACCESS_TOKEN}"
```

**Qué buscar:**
- **Gap grande entre 1d_click y 7d_click:** La conversión ocurre días después del click inicial. Típico en productos de $27-100 donde la persona necesita tiempo. Meta puede estar suboptimizando si el attribution window está en 1d_click.
- **1d_view alto con 1d_click bajo:** El ad convierte pero la gente no hace click — convierten por ver el ad y luego buscar directamente. Indica brand awareness o remarketing fuerte.
- **WhatsApp/Messenger:** Las conversiones siempre aparecen más en 7d_click porque las conversaciones tardan. Evaluar con 7d_click como fuente de verdad para estos objetivos.

### Paso 9: Delivery Quality Check por Ad

Al obtener los insights del Paso 2, extraer para cada ad activo:

| Métrica | Verde | Amarillo | Rojo — Acción |
|---------|-------|----------|---------------|
| quality_ranking | above_average | average | below_average → pausar y reescribir copy |
| engagement_rate_ranking | above_average | average | below_average → cambiar creativo |
| conversion_rate_ranking | above_average | average | below_average → revisar landing/destino |
| Frecuencia | <2.0 | 2.0-3.0 | >3.0 → rotar creativo urgente |
| Hook rate (video) | >30% | 15-30% | <15% → cambiar los primeros 3 segundos |
| Hold rate (video) | >50% | 30-50% | <30% → el contenido no retiene, cambiar estructura |
| LPV rate | >65% | 45-65% | <45% → problema en landing: velocidad, mobile UX o mismatch |
| CPR vs benchmark de cuenta | ≤1x | 1-1.5x | >2x del mejor ad → candidato a pausar |

### Paso 10: Análisis de Audiencias Personalizadas

```bash
# Ver todas las custom audiences disponibles
curl -s "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/customaudiences?fields=id,name,subtype,approximate_count,data_source&access_token=${META_ACCESS_TOKEN}"
```

**Qué buscar:**
- ¿Están siendo utilizadas las audiencias warm en los ad sets BOF?
- ¿El tamaño de la audiencia es suficiente para el presupuesto? (regla: mínimo 1,000 personas por $5/día de presupuesto)
- ¿Hay audiencias vencidas o sin actualizar (approximate_count = 0)?
- ¿El LLA está basado en una fuente de calidad (purchasers, no page likes)?

### Paso 11: Síntesis y Output de Auditoría

Presentar siempre en este orden:

**1. Tabla de performance por ad** (spend, %, CTR, CPM, freq, resultado primario, CPR, quality ranking)

**2. Tabla por segmento demográfico** (edad x sexo, spend, CPR, conversiones — identificar quién convierte mejor)

**3. Tabla por plataforma x placement** (spend, CPM, CTR, conversiones — identificar placements rentables vs drenajes)

**4. Tabla por dispositivo** (iphone, android, desktop — spend, conversiones, CPR con nota de limitación iOS si aplica)

**5. Tabla por región top 10** (spend, %, CPR — flag si un estado >35% del gasto)

**6. Tabla hora del día** (spend vs conversiones por bloque horario — identificar ventanas de performance)

**7. Ganadores confirmados** — ads/segmentos con CPR consistentemente bajo, alta calidad de delivery

**8. Drenajes confirmados** — ads/segmentos con spend alto y resultado malo o nulo

**9. Riesgos operativos** — frecuencias altas, concentración geográfica, pixel sin señal, attribution gaps

**10. Acciones priorizadas** — ordenadas por impacto potencial en CPR o eficiencia de gasto:
- URGENTE (esta semana): pausar X, corregir Y
- CORTO PLAZO (7-14 días): crear ad set Z, testear ángulo W
- OPTIMIZACIÓN ONGOING: rotar creativos, ad schedule, geo segmentation

### Notas técnicas de la API

- Algunos breakdowns no se pueden combinar: `hourly_stats` no se puede mezclar con `age,gender` en la misma llamada. Hacer llamadas separadas.
- `impression_device` puede dar error en algunos objetivos — si falla, intentar con `device_platform` como fallback (da `mobile` vs `desktop`).
- Para `video_thruplay_watched_actions` y métricas de video: solo disponibles cuando el ad usa video. Para statics estos campos estarán vacíos.
- Los `quality_ranking`, `engagement_rate_ranking` y `conversion_rate_ranking` solo están disponibles a nivel de ad, no de ad set o campaña.
- Attribution window en la misma llamada: pasar `action_attribution_windows=['1d_click','7d_click','1d_view']` como campo adicional. Meta devuelve el array de acciones con el window especificado.

---

## Step-by-Step Workflow

### Step 0: Health check inicial OBLIGATORIO — portfolio completo

**PRIMERO, antes de cualquier pregunta**, ejecutar este bloque de inicialización. Es OBLIGATORIO y no se puede saltar. Ricardo opera múltiples cuentas (AION + clientes), y cada sesión empieza con visibilidad completa del portfolio.

#### Paso 0.1 — Source `.env` y verificar token

```bash
set -a && source /c/Users/laroc/.env && set +a
echo "Token: ${META_ACCESS_TOKEN:0:25}..."
```

#### Paso 0.2 — Listar TODAS las cuentas que el token ve (no asumir, no hardcodear)

```bash
curl -s "https://graph.facebook.com/v22.0/me/adaccounts?fields=account_id,name,account_status&limit=20&access_token=${META_ACCESS_TOKEN}"
```

Si el token falla (error 190 = expirado, error 200 = scope incorrecto), detener y pedir regenerar desde Graph API Explorer con app AION LAB.

#### ⚠️ Importante: System User Tokens y endpoints `/me*`

El token de Ricardo (app AION LAB) es **SYSTEM_USER permanente**, no User Token. Esto cambia qué endpoints aplican:

| Endpoint | User Token | System User Token (el de Ricardo) |
|---|---|---|
| `/me` | ✅ | ❌ error 2500 — **ESPERADO, no es bug** |
| `/me/permissions` | ✅ | ❌ error 2500 — **ESPERADO** |
| `/me/adaccounts` | ✅ | ✅ |
| `/act_XXX?fields=name` | ✅ | ✅ |
| `/act_XXX/campaigns` | ✅ | ✅ |
| `/debug_token` | ✅ | ✅ devuelve `type: SYSTEM_USER` |

**NUNCA diagnosticar el token como "roto" basado en `/me` fallando.** El test correcto de validez es:

1. `/me/adaccounts` devuelve >0 cuentas
2. `/act_XXX?fields=name,account_status` funciona para cada cuenta detectada
3. `/debug_token?input_token=X&access_token=X` devuelve `is_valid: True`

Si `/me/adaccounts` falla pero algún `/act_XXX` falla con error 200 "valid app ID required" → ahí sí hay un problema real de app-account asset assignment.

#### Paso 0.3 — Cargar memorias relevantes

Estas memorias persistentes deben consultarse antes de cualquier acción:

- `project-meta-ads-portfolio` — qué cuentas existen, cliente de cada una, vertical
- `reference-aion-technical-ids` — pixel, pages, custom audiences, WhatsApp number, creatives base de AION
- `feedback-aion-whatsapp-template` — welcome message exacto que dispara GHL workflow
- `project-aion-alumnos-count` — número de alumnos vigente para copies
- `feedback-output-style-data-tables` — formato de reportes (tablas, no texto largo)

#### Paso 0.4 — Para cada cuenta accesible, hacer fetch rápido de stats live (en paralelo)

Por cada `act_XXX` listado en Paso 0.2:

```bash
curl -s "https://graph.facebook.com/v22.0/act_XXX/campaigns?fields=id,effective_status,daily_budget&limit=100&access_token=${META_ACCESS_TOKEN}"
```

Contar:
- Total campaigns
- Campaigns ACTIVE
- Suma de daily_budget de las ACTIVE (USD)

#### Paso 0.5 — Mostrar tabla compacta del portfolio al inicio

Output obligatorio antes de cualquier pregunta al usuario:

```
## Portfolio Meta Ads detectado

| Cliente | Account ID | Total | ACTIVE | $/día activo |
|---|---|---|---|---|
| [nombre live de la API] | act_XXX | N | N | $X.XX |
| [nombre live] | act_XXX | N | N | $X.XX |
| [nombre live] | act_XXX | N | N | $X.XX |

Token: AION LAB system user permanente | scopes OK
```

Si alguna cuenta da error en stats, marcarla como ⚠️ con el error específico, sin asumir que está vacía.

---

### Step 1: Seleccionar modo de operación

Después del health check del Step 0, preguntar al usuario con AskUserQuestion **dos preguntas en la misma ronda**:

1. **¿En qué cuenta vas a operar hoy?** (Opciones generadas dinámicamente de las cuentas detectadas en Step 0.2 — no hardcodear nombres)
2. **¿Qué quieres hacer?**
   - Opción A: Auditar campañas existentes
   - Opción B: Crear nueva campaña
   - Opción C: Editar/optimizar campaña existente

Para la cuenta elegida, actualizar `META_AD_ACCOUNT_ID` para esta sesión (sin modificar el .env). Si es la cuenta AION (`act_1131306845739973`), también cargar IDs específicos de `reference-aion-technical-ids` automáticamente (pixel, pages, audiencias). Para otras cuentas (clientes), verificar pixel + page + WhatsApp number antes de operar (no asumir mismos IDs).

---

#### Si elige **Auditar campañas existentes** → Flujo de auditoría

Ejecuta la auditoría completa siguiendo el bloque **Auditing Existing Campaigns** más adelante en este skill. **Foco solo en campañas ACTIVE** salvo que el usuario pida explícitamente histórico de pausadas (regla `feedback-output-style-data-tables`).

---

#### Si elige **Crear nueva campaña** → Flujo de creación

Pregunta al usuario con AskUserQuestion (una ronda, múltiples preguntas):

1. **Producto/servicio:** What are you advertising? Brief description.
2. **Audiencia objetivo:** Who is the target audience? (demographics, interests, pain points)
3. **Presupuesto diario:** Daily budget in USD (ENFORCE max $50/day — reject anything above)
4. **Landing page URL:** Where does the ad send traffic?
5. **Objetivo de campaña:** What's the goal?
   - OUTCOME_LEADS (lead generation)
   - OUTCOME_TRAFFIC (website traffic)
   - OUTCOME_SALES (conversions/purchases)
   - OUTCOME_AWARENESS (brand awareness)
   - OUTCOME_ENGAGEMENT (post engagement)
6. **Destino:** Where do clicks go? (Website, WhatsApp, Messenger, Skool)
7. **Imagen(es)/Video(s):** URL(s) or local file path(s) for the ad creative(s). The user provides these.

---

### Step 2: Design Campaign Strategy

Based on the inputs, design the **optimal campaign structure**. Think like an expert media buyer:

**Campaign Level:**
- Use CBO (Campaign Budget Optimization) — set `daily_budget` at campaign level
- `bid_strategy: LOWEST_COST_WITHOUT_CAP`
- Follow professional naming convention

**Ad Sets (1-3 depending on budget and strategy):**
- For retargeting: 1 ad set combining warm audiences
- For prospecting: 1-2 ad sets with different audience segments
- Use **Advantage+ placements** (automatic) unless user specifies otherwise
- Set `billing_event: IMPRESSIONS` and appropriate `optimization_goal`

**Ads (2-3 per ad set with UNIQUE angles):**
- Each ad has a **completely different copy angle** (Pain/Transformation/Urgency)
- Each ad has a **unique headline** — NEVER use the same headline twice
- Vary CTA button types
- All copy in **Spanish** unless the user specifies otherwise
- CTA button options: `LEARN_MORE`, `SIGN_UP`, `GET_QUOTE`, `CONTACT_US`, `SHOP_NOW`, `BOOK_TRAVEL`, `SUBSCRIBE`, `MESSAGE_PAGE`, `WHATSAPP_MESSAGE`

---

### Step 3: Show Preview for Approval

Before making ANY API calls, display a complete preview with FULL ad copy (not truncated):

```
## Campaign Preview: [Professional Campaign Name]

**Objetivo:** [objective]
**Presupuesto total:** $[budget]/día (CBO — Meta distribuye)
**Estado:** PAUSED (se crea pausada)

### Ad Set: [Professional Ad Set Name]
**Audiencia:** [targeting description]
**Edad:** [age range] | **Geo:** [locations]
**Optimización:** [optimization_goal]
**Plataformas:** [all/specific]

  **Ad A — "[Hook]"**
  Headline: [headline]
  Copy: [FULL primary text — show everything]
  Description: [description]
  CTA: [button type]

  **Ad B — "[Hook]"**
  [... same with DIFFERENT angle ...]

  **Ad C — "[Hook]"**
  [... same with DIFFERENT angle ...]

---
Total: [X] ad set × [Y] ads = [Z] anuncios
```

Ask for confirmation: "Are you ready to create this campaign? (Yes/No/Adjust)"

**Do NOT proceed until the user explicitly approves.**

---

### Step 4: Upload Image(s)

For each image the user provided:

If the image is a **URL**, download it first, then upload to Meta:

```bash
# Download image
curl -L -o "$TEMP/ad_image.jpg" "[IMAGE_URL]"

# Upload to Meta Ads
curl -X POST "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/adimages" \
  -H "Authorization: Bearer ${META_ACCESS_TOKEN}" \
  -F "filename=@$TEMP/ad_image.jpg"
```

If the image is a **local file path**, upload directly:

```bash
curl -X POST "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/adimages" \
  -H "Authorization: Bearer ${META_ACCESS_TOKEN}" \
  -F "filename=@[LOCAL_PATH]"
```

**IMPORTANT (Windows):** Use `$TEMP` for temp files, not `/tmp/`. Paths use forward slashes in bash.

**Save the `image_hash`** from the response — needed for ad creatives.

---

### Step 5: Create Campaign

```bash
curl -X POST "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/campaigns" \
  -H "Authorization: Bearer ${META_ACCESS_TOKEN}" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "[PROFESSIONAL_CAMPAIGN_NAME]",
    "objective": "[OBJECTIVE]",
    "status": "PAUSED",
    "special_ad_categories": [],
    "daily_budget": [BUDGET_IN_CENTS],
    "bid_strategy": "LOWEST_COST_WITHOUT_CAP"
  }'
```

**Save the `campaign_id`** from the response.

If the product involves credit, employment, housing, or social/political issues, set `special_ad_categories` accordingly: `["CREDIT"]`, `["EMPLOYMENT"]`, `["HOUSING"]`, or `["ISSUES_ELECTIONS_POLITICS"]`.

---

### Step 6: Create Ad Sets

For each ad set in the strategy:

**For Prospecting (TOF):**
```bash
curl -X POST "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/adsets" \
  -H "Authorization: Bearer ${META_ACCESS_TOKEN}" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "[PROFESSIONAL_ADSET_NAME]",
    "campaign_id": "[CAMPAIGN_ID]",
    "billing_event": "IMPRESSIONS",
    "optimization_goal": "[OPTIMIZATION_GOAL]",
    "bid_strategy": "LOWEST_COST_WITHOUT_CAP",
    "targeting": {
      "geo_locations": {"countries": ["US"]},
      "age_min": 25,
      "age_max": 65,
      "targeting_automation": {"advantage_audience": 1}
    },
    "promoted_object": {"page_id": "[PAGE_ID]"},
    "destination_type": "[MESSENGER|WHATSAPP|null]",
    "status": "PAUSED",
    "start_time": "[ISO_8601_TOMORROW]"
  }'
```

**For Retargeting (BOF):**
```bash
curl -X POST "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/adsets" \
  -H "Authorization: Bearer ${META_ACCESS_TOKEN}" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "[PROFESSIONAL_ADSET_NAME]",
    "campaign_id": "[CAMPAIGN_ID]",
    "billing_event": "IMPRESSIONS",
    "optimization_goal": "OFFSITE_CONVERSIONS",
    "bid_strategy": "LOWEST_COST_WITHOUT_CAP",
    "targeting": {
      "geo_locations": {"countries": ["US"]},
      "age_min": 25,
      "age_max": 65,
      "custom_audiences": [
        {"id": "[AUDIENCE_ID_1]"},
        {"id": "[AUDIENCE_ID_2]"}
      ],
      "targeting_automation": {"advantage_audience": 0}
    },
    "promoted_object": {
      "pixel_id": "${META_PIXEL_ID}",
      "custom_event_type": "PURCHASE"
    },
    "status": "PAUSED",
    "start_time": "[ISO_8601_TOMORROW]"
  }'
```

**Notes on targeting:**
- `daily_budget` is in **cents** (e.g., $25/day = 2500) — only set at ad set level if NOT using CBO
- When using CBO, do NOT set `daily_budget` on ad sets
- When using `advantage_audience: 1`, `age_max` MUST be 65 (Meta hard requirement)
- When using `advantage_audience: 0` (retargeting), you can set any age range
- For interest targeting, search for interest IDs first:
  ```bash
  curl "https://graph.facebook.com/v22.0/search?type=adinterest&q=[KEYWORD]&access_token=${META_ACCESS_TOKEN}"
  ```
- `start_time` should be set to tomorrow at midnight in the user's timezone

**Save each `adset_id`** from the responses.

---

### Step 7: Create Ad Creatives & Ads

**CRITICAL — UTF-8 Encoding on Windows:**
Spanish ad copy contains accented characters (á, é, í, ó, ú, ñ, ¿, ¡) and emojis that WILL be corrupted if passed through curl `-d` or shell string interpolation on Windows. **NEVER use curl -d with inline JSON containing Spanish text on Windows.**

Instead, ALWAYS use this method:
1. Use the **Write tool** to create a `.json` file with the full payload (the Write tool preserves UTF-8 perfectly)
2. Send the file with `curl --data-binary @file.json`
3. Delete the temp file after

Example:
```bash
# Step 1: Write the JSON file using the Write tool (NOT echo/cat/heredoc)
# Step 2: Send it
curl -s -X POST "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/adcreatives" \
  -H "Authorization: Bearer ${META_ACCESS_TOKEN}" \
  -H "Content-Type: application/json; charset=utf-8" \
  --data-binary @/path/to/creative_payload.json
# Step 3: Clean up
rm -f /path/to/creative_payload.json
```

This applies to ALL API calls that contain Spanish text: creatives, ad names, campaign names, ad set names. For API calls with only English text or IDs (like creating campaigns, ad sets without copy), regular curl is fine.

For each ad variation in each ad set:

**7a. Create the Ad Creative:**

Use the Write tool to create a JSON file with this structure, then send with `curl --data-binary @file.json`:

```json
{
  "name": "[PROFESSIONAL_CREATIVE_NAME]",
  "object_story_spec": {
    "page_id": "[PAGE_ID]",
    "link_data": {
      "message": "[PRIMARY_TEXT — FULL PROFESSIONAL COPY]",
      "link": "[LANDING_PAGE_URL]",
      "image_hash": "[IMAGE_HASH]",
      "name": "[UNIQUE_HEADLINE]",
      "description": "[DESCRIPTION]",
      "call_to_action": {
        "type": "[CTA_TYPE]",
        "value": {"link": "[LANDING_PAGE_URL]"}
      }
    }
  }
}
```

**7b. Create the Ad:**

```bash
curl -X POST "https://graph.facebook.com/v22.0/${META_AD_ACCOUNT_ID}/ads" \
  -H "Authorization: Bearer ${META_ACCESS_TOKEN}" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "[PROFESSIONAL_AD_NAME]",
    "adset_id": "[ADSET_ID]",
    "creative": {"creative_id": "[CREATIVE_ID]"},
    "status": "PAUSED"
  }'
```

**Save all `creative_id` and `ad_id` values.**

---

### Step 8: Display Results

Show the complete summary:

```
## Campaign Created Successfully

**Campaign:** [professional name] (ID: [campaign_id])
**Estado:** PAUSED
**Presupuesto total:** $[budget]/día (CBO)

| Ad Set | Audiencia | Optimización | Ads |
|--------|-----------|-------------|-----|
| [name] (ID: [id]) | [targeting summary] | [opt goal] | [count] ads |

### All Ad IDs:
| Ad | Angle | ID |
|----|-------|----|
| [name] | [Pain/Transform/Urgency] | [ad_id] |

### Next Steps:
1. Go to Meta Ads Manager to review the campaign
2. Replace placeholder images with your UGC videos for best performance
3. When ready, change the campaign status to ACTIVE
```

---

## Hard Rules

- **NEVER** create a campaign with daily budget above $50 USD. If the user asks for more, refuse and explain the limit.
- **NEVER** create campaigns in ACTIVE status. Always PAUSED.
- **NEVER** skip the preview/confirmation step. Always show the full structure and wait for approval.
- **NEVER** make API calls without valid environment variables. Check they exist before starting.
- **NEVER** duplicate ad copy between ads. Each ad MUST have a unique angle and headline.
- **NEVER** use default names like "New Sales Ad Set" or "New Engagement Ad - Copy 2".
- **NEVER** have grammatical errors in Spanish copy. Double-check: enseñar, estás, detrás, más, sí/si, qué/que.
- **NEVER** send Spanish ad copy through curl `-d` inline on Windows — characters WILL be corrupted. ALWAYS write JSON payloads to a file using the Write tool and send with `curl --data-binary @file.json`. This is NON-NEGOTIABLE.
- **ALWAYS** use professional naming convention for ALL entities.
- **ALWAYS** write copy at professional copywriter level — specific, compelling, error-free.
- **ALWAYS** show FULL copy in previews, not truncated.
- **All ad copy in Spanish** unless the user explicitly requests another language.
- If any API call fails, show the error, explain what went wrong, and ask the user how to proceed. Do NOT retry blindly.
- For products involving credit, employment, housing, or social/political topics, check if `special_ad_categories` needs to be set accordingly.
- UGC video ads (face to camera) outperform static images 2-3x. Always recommend video when available.
- For OUTCOME_ENGAGEMENT with Messenger/WhatsApp, the `POST_ENGAGEMENT` optimization goal does NOT work. Use `CONVERSATIONS` instead.
- The AION LAB app must be in **Live mode** (not Development) to create ad creatives via API. If you get error 1885183, tell user to publish the app.

## Error Handling

- If `META_ACCESS_TOKEN` is missing or expired (error code 190): tell the user to regenerate from Graph API Explorer > App: AION LAB. Tokens last ~1 hour.
- If `META_AD_ACCOUNT_ID` is invalid: guide user to find it in Business Settings
- If image upload fails: check file format (JPG/PNG required, max 30MB)
- If targeting interest search returns empty: suggest broader terms
- If ad set creation fails with budget error: the minimum daily budget per ad set is typically $1/day
- If optimization_goal is rejected: check the compatibility table above. OUTCOME_ENGAGEMENT does NOT support POST_ENGAGEMENT.
- If `advantage_audience` error: age_max must be 65 when advantage_audience=1
- If "app in development mode" error (1885183): user must publish the app in developers.facebook.com
- If "authenticate your account" error (3858385): user must verify identity in Ads Manager. This happens after many rapid API calls. Wait a few minutes or generate a new token.
- If WhatsApp Business required (2923012): cannot modify WhatsApp ads via API with user tokens. Provide copy for manual update in Ads Manager.
