Aquí está la versión completamente gratuita, adaptada a costo cero real:

---

## Stack tecnológico — $0 absolutos

Cada herramienta reemplaza a su versión de pago:

- Google Colab → reemplaza instalar Python local (nada que instalar, nada que pagar)
- Google Sheets → reemplaza Supabase/PostgreSQL (base de datos ilimitada y gratis)
- Google My Maps → reemplaza Google Maps API de pago (visualización gratuita)
- n8n self-hosted en Render.com → reemplaza flujos de automatización de pago
- Bot de Telegram → reemplaza la interfaz web (más fácil, más rápido, gratis)
- Render.com free tier → reemplaza Railway/Vercel de pago
- Claude.ai plan gratuito → para el MVP inicial antes de tener ingresos
- Yape / Plin → reemplaza Stripe y MercadoPago (0% de comisión)
- GitHub → control de versiones (siempre gratis)

---

## Plan día a día — versión $0

### Semana 1: Datos a mano (días 1–7)

**Día 1** — Crea una cuenta en Google (si no tienes). Abre Google Sheets y crea tu primera hoja llamada `departamentos_lima`. Crea estas columnas: distrito, precio_venta_usd, alquiler_mensual_usd, metros2, dormitorios, fuente, fecha.

**Día 2** — Entra a Urbania.pe y busca "departamento 1 dormitorio Lima precio máximo $70,000". Anota a mano 30 resultados en tu hoja. No necesitas código, solo copiar y pegar los datos importantes.

**Día 3** — Repite en Adondevivir.com. Busca también en OLX.com.pe y en los grupos de Facebook "Inmuebles Lima", "Inversiones inmobiliarias Perú". Meta del día: 80 registros en total.

**Día 4** — Añade una columna "alquiler_mensual". Para los departamentos donde solo ves precio de venta, entra a Urbania y busca alquileres similares en el mismo distrito para estimar. Anota la fuente.

**Día 5** — Crea una segunda hoja llamada `distritos`. Agrupa tus datos por distrito con fórmulas simples de Google Sheets: `=PROMEDIO` y `=CONTAR`. Identifica los 10 distritos con más registros.

**Día 6** — Abre Google My Maps (maps.google.com → crear mapa). Importa tu hoja de distritos. Colorea cada distrito por precio promedio. Esto es tu primer mapa de calor, sin pagar nada.

**Día 7** — Valida: compara tus datos con los precios que conoces de tu entorno o con lo que te digan en grupos de WhatsApp de inversores. Corrige errores evidentes.

---

### Semana 2: Análisis en Google Colab (días 8–14)

**Día 8** — Abre colab.research.google.com (gratis, sin instalar nada). Crea un nuevo notebook. Conecta tu Google Sheet al Colab con este código de 3 líneas que te daré cuando llegues a este paso.

**Día 9** — Escribe en Colab la fórmula de rentabilidad bruta:
`rentabilidad = (alquiler_mensual * 12) / precio_venta * 100`
Aplícala a toda tu tabla con pandas. Es 5 líneas de código, puedes hacerlo aunque sepas poco.

**Día 10** — Calcula rentabilidad neta restando gastos estimados: predial (0.2% anual del valor), vacancia (8%), mantenimiento (1.5% anual). Añade una columna `score_neto`.

**Día 11** — Ordena los distritos de mayor a menor rentabilidad neta. Guarda el resultado como nueva hoja en tu Google Sheet. Ya tienes tu primer ranking real de Lima.

**Día 12** — Identifica los patrones: para el rango $50,000–$70,000 en Lima, los distritos con mejor rentabilidad suelen ser Jesús María, Lince, Breña, La Victoria (zonas B+) y San Miguel. Anota cuáles aparecen en tu ranking.

**Día 13** — Añade en Colab una visualización simple con `matplotlib` (incluido en Colab, gratis): gráfico de barras con rentabilidad por distrito. Guárdalo como imagen.

**Día 14** — Redacta en Google Docs un resumen de 2 páginas con tus hallazgos. Este documento será el "cerebro" de tu agente.

---

### Semana 3: El agente con herramientas gratuitas (días 15–21)

**Día 15** — Crea una cuenta en Telegram (si no tienes) y en BotFather crea tu primer bot. En menos de 10 minutos tienes una interfaz de chat funcional sin pagar nada.

**Día 16** — Instala n8n en Render.com (tiene free tier). n8n es un sistema de automatización visual que conecta piezas sin mucho código. Crea una cuenta en render.com, despliega n8n siguiendo su guía de un clic.

**Día 17** — En n8n conecta tres piezas: Telegram (recibe la pregunta del usuario) → Google Sheets (busca los datos) → Claude.ai vía webhook (genera la respuesta). Hay tutoriales en YouTube para esto.

**Día 18** — Escribe el "system prompt" de tu agente: un texto que le explica a Claude quién es, qué datos tiene, y cómo debe responder. Este prompt es lo más importante del agente y no cuesta nada.

**Día 19** — Prueba el flujo completo: escríbele al bot de Telegram "¿Dónde compro un departamento de $60,000 en Lima para alquilar?". El bot debe responder con datos reales de tu Google Sheet.

**Día 20** — Ajusta el prompt según las respuestas del día anterior. Si el agente dice cosas raras, modifica el prompt para que sea más preciso. Itera 5–10 veces.

**Día 21** — Prueba con 10 preguntas reales que haría un inversor. Documenta las 3 preguntas que el agente no responde bien y corrígelas.

---

### Semana 4: El producto (días 22–28)

**Día 22** — Tu producto en esta etapa es simple: alguien te escribe por Telegram, el bot responde automáticamente con recomendaciones de zonas en Lima basadas en tus datos reales. No necesitas web, no necesitas app.

**Día 23** — Escribe en Google Docs tu "propuesta de valor" en 3 líneas: qué problema resuelve, para quién es, y cuánto cuesta. Ejemplo: "Agente IA que analiza las mejores zonas de Lima para comprar departamentos de $50k–$80k y maximizar tu rentabilidad de alquiler. Para inversores que no quieren perder tiempo investigando. S/50 por consulta completa."

**Día 24** — Crea una cuenta en Canva (gratuita) y diseña una imagen de presentación del agente. Publícala en tu perfil de Facebook y LinkedIn con la propuesta de valor.

**Día 25** — Crea un grupo de WhatsApp llamado "Inversión inmobiliaria Lima – [tu nombre]". Invita a 20 personas de tu red que puedan estar interesadas o que conozcan a alguien interesado.

**Día 26** — Publica en el grupo la imagen de Canva y el enlace a tu bot de Telegram. Ofrece las primeras 3 consultas gratis a cambio de feedback escrito.

**Día 27** — Define cómo cobrarás: S/50 por consulta única (la persona te escribe, el bot responde, tú confirmas por Yape). Sin contratos, sin plataformas, sin comisiones.

**Día 28** — Prepara una respuesta rápida de WhatsApp para cuando alguien te pregunte: "¿Cómo funciona?" que explique el proceso en 3 pasos simples.

---

### Semanas 5–6: Primeros ingresos y escala (días 29–42)

**Días 29–31** — Contacta directamente a 30 personas de tu red: familiares, amigos, ex compañeros de trabajo. El mensaje es simple: "Estoy lanzando un agente IA de inversión inmobiliaria en Lima. ¿Conoces a alguien que esté pensando en comprar un depa para alquilar?" No pidas dinero todavía, pide referencias.

**Días 32–34** — De esas 30 personas, al menos 5 te darán un nombre. Escríbeles directamente y ofréceles la primera consulta gratis. Tu meta: 3 personas que usen el bot y te den feedback honesto.

**Días 35–37** — Con el feedback de las 3 personas, mejora el prompt del agente y actualiza los datos de tu Google Sheet. Luego ofrece a esas mismas 3 personas un plan mensual a S/30/mes por consultas ilimitadas. Si 2 aceptan, ya tienes S/60/mes.

**Días 38–40** — Con S/60, ya puedes pagar el primer mes de la API de Anthropic (~$5 dólares ≈ S/18). Activa la API para que el agente sea más rápido y sin los límites del plan gratuito de Claude.ai. Mantén Render.com gratuito por ahora.

**Días 41–42** — Automatiza la actualización semanal de datos: cada lunes dedica 1 hora a revisar Urbania y actualizar tu Google Sheet con los precios nuevos. El agente mejora automáticamente porque lee la misma hoja.

---

## La diferencia clave con la versión anterior

En lugar de gastar en APIs desde el día 1, aquí usas Claude.ai gratuito + n8n + Google Sheets como sustitutos funcionales. El producto es exactamente el mismo para el usuario (un bot que responde preguntas sobre inversión en Lima), pero tú no pagas nada hasta que tengas ingresos reales. Cuando llegues a S/50 de ingresos, activas la API de Anthropic y el sistema escala sin cambiar nada más.

Haz clic en cualquier caja del diagrama para profundizar en ese paso.
