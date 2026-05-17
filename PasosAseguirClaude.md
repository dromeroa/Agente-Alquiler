Aquí está tu plan completo. Primero el flujo visual, luego el detalle día a día.Ahora aquí está el plan completo con todos los ingredientes y actividades por día:

---

## Los ingredientes (stack tecnológico gratuito o casi gratis)

**Herramientas principales** — todas tienen free tier suficiente para empezar:

- Python 3.11 (lenguaje principal, gratis)
- Claude API de Anthropic (el motor de IA, ~$5 de crédito gratuito al inicio)
- Supabase (base de datos PostgreSQL gratuita, 500MB)
- Vercel o Railway (despliegue web gratuito)
- BeautifulSoup + Requests (scraping de Urbania y Adondevivir, gratis)
- Streamlit (interfaz web en Python puro, gratis) — para el MVP
- Google Maps API (capa gratuita de $200/mes es más que suficiente al inicio)
- GitHub (control de versiones, gratis)
- Stripe o MercadoPago (pagos, solo cobran comisión al vender)

**Costo total para empezar: menos de $10 dólares** (solo el uso de la API de Claude).

---

## Plan día a día — 42 días

### Semana 1: Datos (días 1–7)

**Día 1** — Instala Python, crea cuenta en GitHub, Supabase y Anthropic. Lee la documentación básica de la Claude API (30 min).

**Día 2** — Escribe tu primer script Python que hace scraping de Urbania.pe buscando departamentos de 1–2 dormitorios entre $50k–$80k en Lima. Guarda los resultados en un CSV.

**Día 3** — Amplía el scraping a Adondevivir.com. Añade campos: precio de venta, precio de alquiler, distrito, metraje, antigüedad. Meta: 200+ registros.

**Día 4** — Limpia los datos: elimina duplicados, normaliza distritos (Miraflores vs miraflores vs MIRAFLORES), convierte precios a USD.

**Día 5** — Sube los datos limpios a Supabase. Crea la tabla `departamentos` con campos básicos.

**Día 6** — Activa Google Maps API. Geolocaliza cada departamento (coordenadas lat/lng) y añade datos de cercanía a metro, supermercados, universidades.

**Día 7** — Revisa y valida: ¿tienen sentido los precios? Compara manualmente con 5–10 departamentos reales que conozcas.

---

### Semana 2: Análisis (días 8–14)

**Día 8** — Calcula la **rentabilidad bruta** por departamento: `(alquiler mensual × 12) / precio de venta × 100`. Un buen número en Lima es entre 5% y 8%.

**Día 9** — Añade gastos típicos: impuesto predial (~0.2% del valor), mantenimiento (~1.5% anual), vacancia estimada (~8%). Calcula rentabilidad neta.

**Día 10** — Agrupa por distrito y calcula: precio promedio por m², alquiler promedio, rentabilidad promedio. Identifica los top 10 distritos.

**Día 11** — Crea un score ponderado por zona considerando: rentabilidad (40%), liquidez del mercado (30%), plusvalía histórica (30%). Usa datos del INEI para la plusvalía.

**Día 12** — Genera tu primer reporte: un CSV con el ranking de distritos ordenado por score. Incluye La Victoria, Jesús María, Breña, Lince y San Miguel — suelen tener mejor rentabilidad que Miraflores para departamentos de $60k.

**Día 13** — Visualiza en un mapa con Folium (librería Python gratuita): cada distrito coloreado por score de rentabilidad.

**Día 14** — Valida con 2–3 personas del sector inmobiliario (agentes de Urbania, Facebook groups de inversores peruanos). Ajusta pesos si es necesario.

---

### Semana 3: El Agente IA (días 15–21)

**Día 15** — Crea tu primera llamada a la Claude API. Envíale una pregunta simple: "¿Dónde debo comprar un departamento de $60k en Lima para alquilar?". Observa la respuesta sin datos reales.

**Día 16** — Conecta Claude con tu base de datos: dale acceso a los datos de Supabase para que sus respuestas estén basadas en datos reales de Lima, no en suposiciones generales.

**Día 17** — Añade la primera "tool" (función que Claude puede llamar): `buscar_departamentos(distrito, precio_max, precio_min)`. Claude decide cuándo y cómo llamarla.

**Día 18** — Añade segunda tool: `calcular_rentabilidad(precio_compra, alquiler_mensual, gastos)`. Ahora el agente puede hacer cálculos personalizados.

**Día 19** — Añade tercera tool: `ranking_zonas(presupuesto)`. Dado un presupuesto, devuelve el top 5 de zonas recomendadas.

**Día 20** — Añade memoria básica: guarda el historial de la conversación para que el agente recuerde qué ya discutió con el usuario en la misma sesión.

**Día 21** — Prueba el agente 20 veces con preguntas reales que haría un inversor. Corrige los errores más frecuentes en el system prompt.

---

### Semana 4: El Producto (días 22–28)

**Día 22** — Instala Streamlit (`pip install streamlit`). Crea una interfaz web mínima: caja de chat + botón de enviar + historial de mensajes. Una tarde es suficiente.

**Día 23** — Añade un panel lateral con filtros: presupuesto máximo, tipo (1 dorm. / 2 dorm.), zona preferida, objetivo (máxima rentabilidad / menor riesgo).

**Día 24** — Conecta la interfaz con tu agente Claude. Prueba que todo funcione end-to-end: usuario escribe → agente consulta datos → responde con recomendaciones.

**Día 25** — Despliega en Streamlit Cloud (gratis, 1 comando). Tienes una URL pública para compartir.

**Día 26** — Define tu modelo de negocio. Opción más simple: plan gratuito (5 consultas/mes) y plan Pro a $29/mes (ilimitado + reporte PDF). Crea las cuentas en Stripe o MercadoPago.

**Día 27** — Añade autenticación básica con Supabase Auth (email + contraseña). Relaciona cada usuario con su plan y su límite de consultas.

**Día 28** — Crea una landing page de 1 página en Notion o Carrd.co (gratuito) explicando qué hace el agente, para quién es y cuánto cuesta.

---

### Semanas 5–6: Mercado y Escala (días 29–42)

**Días 29–31** — Consigue tus primeros 5 usuarios beta gratis. Búscalos en: grupos de Facebook de inversión inmobiliaria en Perú, LinkedIn buscando "inversor inmobiliario Lima", foros de Urbania, WhatsApp de tu red personal.

**Días 32–34** — Recoge feedback estructurado: ¿qué les falta? ¿qué no entienden? ¿qué les sorprendió? Prioriza los 3 cambios más pedidos e impleméntalos.

**Días 35–37** — Activa el modelo de pago. Ofrece a tus 5 betas un precio de fundador ($15/mes en vez de $29). La meta es tu primer dólar real.

**Días 38–40** — Automatiza la actualización de datos: un script Python que corra cada semana y actualice precios de Urbania automáticamente (cron job en Railway, gratis).

**Días 41–42** — Diseña la arquitectura multicliente: cada cliente tiene su propio "espacio" en Supabase. Documenta cómo añadir una nueva ciudad (Arequipa, Cusco) en menos de 2 días de trabajo.

---

## La fórmula de rentabilidad clave para tu agente

Para departamentos de $60,000 en Lima, el agente debe buscar zonas donde:

- El alquiler mensual sea **al menos $350–$400** (rentabilidad bruta ≥ 7%)
- Los distritos con mejor ratio histórico para ese rango son Jesús María, Lince, La Victoria (zonas consolidadas), Breña y San Miguel
- Evitar Miraflores y San Isidro para ese presupuesto (precio muy alto, rentabilidad bruta 4–5%)

---

## Para escalar y llevarlo al mercado

El agente es escalable porque la arquitectura separa los datos (Supabase), el motor de IA (Claude API), y la interfaz (Streamlit/Next.js). Para añadir un nuevo cliente o ciudad solo cambias el dataset, no el código. El modelo SaaS por suscripción te permite crecer sin costos fijos proporcionales — cada nuevo cliente agrega ingresos pero solo un pequeño incremento en costos de API.

Haz clic en cualquier caja del flujo para profundizar en ese tema específico.
