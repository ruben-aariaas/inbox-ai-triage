# Inbox AI Triage

## Resumen
Inbox AI Triage es un sistema de triage de mensajes entrantes con IA orientado a soporte, ventas y operaciones.

Recibe mensajes, los clasifica automáticamente, asigna una prioridad, genera un resumen y guarda el resultado de forma estructurada para facilitar una respuesta más rápida y ordenada.

El proyecto está construido con n8n, OpenAI API, JavaScript, Webhooks y Google Sheets.

---

## Problema de negocio
Muchas empresas pequeñas reciben mensajes mezclados en un mismo canal:

- incidencias
- dudas de soporte
- seguimientos
- formularios de contacto
- leads comerciales
- spam o promociones no solicitadas

Cuando esa revisión se hace manualmente, aparecen varios problemas:

- pérdida de tiempo
- mala priorización
- respuestas tardías
- más desorden operativo
- leads que se enfrían
- ruido mezclado con mensajes importantes

---

## Solución
Inbox AI Triage automatiza la primera revisión de mensajes entrantes.

El sistema:

- recibe un mensaje
- lo clasifica por tipo
- asigna una prioridad
- genera un resumen breve
- añade metadatos de ejecución
- guarda el resultado de forma estructurada

De esta forma, la entrada deja de ser caótica y pasa a convertirse en información accionable.

---

## Qué valor aporta
- reduce trabajo manual
- mejora la priorización
- ayuda a responder antes a lo importante
- separa soporte, ventas y spam
- deja trazabilidad de cada ejecución
- sirve como base para escalar a otros canales

---

## Arquitectura general

### Modo evaluación
Se utiliza un dataset de prueba con etiquetas esperadas para medir el comportamiento del sistema y comparar la salida de OpenAI con el resultado esperado.

Flujo:

`Manual Trigger → Dataset de prueba → Add Run Metadata → OpenAI Classification → Parse OpenAI → Merge Original + AI → Evaluate AI Output → Save Results to Google Sheets`

### Modo real
Se utiliza un webhook para recibir mensajes reales y procesarlos sin necesidad de labels esperados.

Flujo:

`Incoming Message Webhook → Normalize Incoming Message → Add Run Metadata → OpenAI Classification → Parse OpenAI → Merge Original + AI → Save Results to Google Sheets`

---

## Stack
- n8n
- OpenAI API
- JavaScript
- Webhooks
- Google Sheets

---

## Componentes principales

### Incoming Message Webhook
Recibe mensajes reales en formato JSON.

### Normalize Incoming Message
Normaliza la entrada para que el resto del flujo trabaje con una estructura consistente.

### Add Run Metadata
Añade trazabilidad:
- run_id
- fecha_ejecucion
- fuente
- modelo_usado

### OpenAI Classification
Envía el contenido del mensaje al modelo para obtener:
- categoría
- prioridad
- resumen

### Parse OpenAI
Convierte la respuesta del modelo en un objeto limpio y usable.

### Merge Original + AI
Une los datos originales del mensaje con la salida procesada del modelo.

### Evaluate AI Output
Compara la salida del sistema con la clasificación esperada cuando se trabaja en modo evaluación.

### Save Results to Google Sheets
Guarda los resultados para revisión, análisis y demo.

---

## Salida esperada
Cada mensaje procesado puede generar, según el modo:

- run_id
- fecha_ejecucion
- fuente
- modelo_usado
- id
- nombre
- email
- mensaje
- categoria
- prioridad
- resumen
- estado_procesado

En modo evaluación también se añaden:
- categoria_esperada
- prioridad_esperada
- acierto_categoria
- acierto_prioridad
- correcto_total
- error_categoria
- error_prioridad

---

## Casos de uso
- clasificación de formularios de contacto
- triage inicial de soporte
- detección de incidencias
- separación de leads comerciales
- filtrado de spam
- organización de entrada operativa

---

## Demo cases recomendados
El proyecto está pensado para demostrarse con tres tipos de entrada:

1. soporte urgente  
2. lead comercial real  
3. spam o promoción no solicitada  

Esto permite enseñar claramente:
- clasificación
- prioridad
- resumen
- trazabilidad
- valor operativo

---

## Qué demuestra técnicamente
- integración de OpenAI API en un flujo real
- diseño de automatizaciones con n8n
- normalización de entrada
- parseo y validación de respuestas
- trazabilidad por ejecución
- persistencia en Google Sheets
- separación entre entorno de evaluación y entorno real

---

## Qué demuestra a nivel profesional
- pensamiento orientado a negocio
- capacidad de convertir un problema operativo en sistema
- diseño de flujos con entrada real
- preocupación por evaluación y calidad
- documentación y presentación del trabajo

---

## Para quién puede ser útil
- agencias pequeñas
- e-commerce
- clínicas
- despachos
- academias
- equipos con formularios web
- negocios donde varios tipos de mensaje entran mezclados

---

## Limitaciones actuales
- dataset todavía pequeño
- el criterio de prioridad puede afinarse más en algunos casos ambiguos
- todavía no hay integración directa con Gmail o CRM
- no hay autenticación en el webhook de prueba
- la gestión de duplicados puede seguir mejorándose en futuras versiones
- la codificación de algunos caracteres especiales depende del origen del input

---

## Mejoras futuras
- integración con Gmail
- integración con CRM
- autenticación del webhook
- respuestas sugeridas por IA
- dashboard de métricas
- asignación automática por persona o equipo
- analítica por tipo de mensaje
- versiones de prompt comparables
- sistema de evaluación más amplio

---

## Enfoque comercial
Este proyecto no se plantea como “un chatbot” ni como una automatización genérica.

Se plantea como una solución de triage con IA para reducir trabajo manual, mejorar priorización y ordenar la entrada de mensajes en entornos pequeños o medianos.

---

## Frase resumen
Inbox AI Triage convierte una entrada caótica de mensajes en una entrada estructurada, priorizada y accionable.

---

## Próximos pasos
- estabilizar la demo
- grabar un Loom corto
- publicar el caso en LinkedIn
- integrarlo con más canales de entrada
- usarlo como base para outreach y entrevistas
