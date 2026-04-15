# Demo Cases — Inbox AI Triage

## Objetivo
Este documento recoge tres casos de demo diseñados para enseñar el valor del sistema de forma rápida, clara y orientada a negocio.

El proyecto está pensado para demostrar cómo un flujo con IA puede clasificar mensajes entrantes, asignar prioridad, generar un resumen y dejar la información lista para actuar sin revisión manual inicial.

---

## Demo 1 — Soporte urgente

### Contexto
Un usuario no puede acceder a su cuenta y el problema afecta directamente al uso del servicio.

### Input
```json
{
  "nombre": "Carlos Martín",
  "email": "carlos@email.com",
  "mensaje": "No puedo acceder a mi cuenta desde esta mañana y el cambio de contraseña no funciona."
}
Output esperado
Categoría: soporte
Prioridad: alta
Resumen: problema de acceso a la cuenta y fallo en recuperación de contraseña
Qué demuestra
Detección automática de incidencias importantes
Priorización útil para el equipo
Generación de un resumen operativo
Capacidad de reducir tiempo de revisión manual
Valor de negocio

En un entorno real, este tipo de mensaje no debería quedarse mezclado con consultas normales o spam. El sistema permite detectar rápidamente incidencias que requieren atención prioritaria.

Qué se puede enseñar en demo
Entrada del mensaje por webhook
Procesamiento con IA
Resultado estructurado en Google Sheets
Clasificación y prioridad visibles de forma inmediata
Demo 2 — Lead comercial real
Contexto

Una persona interesada en el servicio solicita información comercial para un equipo de tamaño relevante.

Input
{
  "nombre": "Lucía Navarro",
  "email": "lucia@email.com",
  "mensaje": "Hola, me gustaría recibir información sobre vuestros planes para equipos de más de 10 personas."
}
Output esperado
Categoría: ventas
Prioridad: media
Resumen: solicitud comercial sobre planes para equipos grandes
Qué demuestra
Separación entre soporte y oportunidades comerciales
Detección de leads útiles
Priorización razonable sin intervención manual
Aplicación del sistema a equipos comerciales y de operaciones
Valor de negocio

En muchos negocios pequeños, los mensajes comerciales acaban mezclados con consultas, incidencias o spam. Este sistema ayuda a detectar oportunidades reales y reducir el riesgo de perderlas por desorden interno.

Qué se puede enseñar en demo
Recepción del lead
Clasificación automática como ventas
Resumen listo para el equipo
Registro estructurado para seguimiento posterior
Demo 3 — Spam o promoción no solicitada
Contexto

Llega un mensaje promocional irrelevante para el equipo, típico de campañas no solicitadas.

Input
{
  "nombre": "Oferta SEO",
  "email": "seo@spammail.com",
  "mensaje": "Multiplica tus ventas con nuestro servicio SEO garantizado. Resultados en 7 días."
}
Output esperado
Categoría: spam
Prioridad: baja
Resumen: promoción no solicitada de servicios SEO
Qué demuestra
Filtrado de ruido
Capacidad de distinguir una oportunidad comercial real de una promoción irrelevante
Ahorro de tiempo operativo
Limpieza del canal de entrada
Valor de negocio

Uno de los problemas más comunes en empresas pequeñas es que mensajes irrelevantes consumen tiempo y atención. Este sistema ayuda a reducir ese ruido y mejora la concentración del equipo en lo realmente importante.

Qué se puede enseñar en demo
Entrada del mensaje
Clasificación automática como spam
Prioridad baja
Registro del resultado para trazabilidad y revisión
Qué enseña la demo completa

Estos tres ejemplos muestran que el sistema es capaz de:

clasificar mensajes entrantes por tipo
asignar prioridad en función del impacto
generar resúmenes útiles para actuar
reducir trabajo manual en la revisión inicial
diferenciar entre soporte, ventas y ruido
dejar un registro estructurado del procesamiento
