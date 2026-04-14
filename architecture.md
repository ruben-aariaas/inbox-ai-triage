## Payload real del webhook (definitivo)

{
  "nombre": "string",
  "email": "string",
  "mensaje": "string"
}

## Prompt de clasificación (v1)

Clasifica el siguiente mensaje en una de estas categorías:
- soporte
- bug
- ventas
- seguimiento
- spam

Devuelve solo la categoría, sin explicación.

Mensaje:
{{mensaje}}


## Prompt de prioridad (v1)

Asigna una prioridad al siguiente mensaje:
- alta
- media
- baja

Criterios:
- alta: problemas críticos o urgentes
- media: consultas normales o leads
- baja: seguimiento o baja urgencia

Devuelve solo una palabra.

Mensaje:
{{mensaje}}


## Prompt de resumen (v1)

Resume el siguiente mensaje en una frase clara y corta.

Mensaje:
{{mensaje}}


## Flujo técnico v1

1. Webhook recibe datos
2. Validar que mensaje no esté vacío
3. Enviar mensaje a OpenAI → clasificación
4. Enviar mensaje a OpenAI → prioridad
5. Enviar mensaje a OpenAI → resumen
6. Construir objeto final
7. Guardar en Google Sheets


Reglas adicionales:
- Si el mensaje ofrece servicios no solicitados, promesas comerciales agresivas o propuestas genéricas de captación, clasifícalo como spam
- Si el mensaje solo pide actualización sobre un caso anterior, ticket o incidencia ya abierta, clasifícalo como seguimiento
- Los mensajes de seguimiento suelen tener prioridad baja salvo que incluyan urgencia clara o bloqueo actual
- Las consultas de ayuda no urgente o dudas de uso suelen ser soporte con prioridad baja o media según el impacto
- No clasifiques como ventas mensajes promocionales enviados al equipo sin haber sido solicitados por el usuario

{
  "nombre": "Carlos",
  "email": "carlos@email.com",
  "mensaje": "Hola, la aplicación da error al iniciar sesión"
}
