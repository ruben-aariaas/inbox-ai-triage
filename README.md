# Inbox AI Triage

## Problema
Los correos o tickets entran sin clasificar, requieren revisión manual y consumen tiempo operativo en equipos de soporte.

## Usuario
Equipos de soporte, operaciones o atención al cliente que gestionan alto volumen de mensajes.

## Input
Correos entrantes, formularios de contacto o tickets desde herramientas de soporte.

## Flujo
Paso 1: Recepción del mensaje (Gmail, webhook o formulario)  
Paso 2: Clasificación automática por tipo (soporte, bug, ventas, etc.)  
Paso 3: Detección de prioridad (alta, media, baja)  
Paso 4: Extracción de datos clave (nombre, problema, contexto)  
Paso 5: Generación de resumen con IA  
Paso 6: Envío al canal correspondiente (Slack/Telegram/email)  
Paso 7: Registro en base de datos o Google Sheets  

## Output
Ticket clasificado automáticamente con prioridad asignada, resumen generado y notificación al equipo correspondiente.

## Stack
n8n, OpenAI API, Gmail/Webhook, Google Sheets o base de datos, Slack/Telegram.

## Valor de negocio
Reduce el tiempo de gestión manual, mejora la priorización y evita errores en la asignación de tickets.

## Qué demuestra en entrevista
- Integración de APIs  
- Automatización de procesos reales  
- Uso práctico de IA en workflows  
- Pensamiento orientado a negocio  

## Mejoras futuras
- Integración con herramientas como Zendesk o HubSpot  
- Clasificación entrenada con datos históricos  
- Dashboard de métricas de soporte  
- Sistema de respuesta automática básica  
