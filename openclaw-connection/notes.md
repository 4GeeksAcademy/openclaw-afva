cat > openclaw-connection/notes.md <<'EOF'
# Práctica: Integración de OpenClaw

## Objetivo
Configurar un asistente de inteligencia artificial mediante OpenClaw, conectarlo con Telegram e integrar Google Docs y Google Calendar a través de Zapier MCP.

## Entorno tecnológico
- OpenClaw desplegado en un servidor VPS con Ubuntu 22.04.
- Telegram configurado como canal de comunicación con el agente.
- Zapier MCP conectado mediante mcporter.
- Google Docs y Google Calendar autorizados a través de Zapier.

## Implementación
1. Instalación y configuración de OpenClaw en el servidor VPS.
2. Conexión del agente OpenClaw con Telegram.
3. Configuración y autenticación de Zapier MCP mediante mcporter.
4. Habilitación de las acciones de Google Docs y Google Calendar.
5. Pruebas de funcionamiento de ambas integraciones desde Telegram.

## Resultados
- Creación satisfactoria de un documento de Google Docs mediante instrucciones enviadas desde Telegram.
- Creación satisfactoria de un evento en Google Calendar.
- Envío de invitaciones del calendario a tres participantes.
- Verificación de que los participantes recibieron el evento en sus calendarios.

## Evidencias
Las capturas de pantalla se encuentran en el directorio `screenshots/`:

- `Chat_docs_proof.png`: solicitud y respuesta del agente en Telegram.
- `google_docs_proof.png`: documento creado en Google Docs.
- `Chat_Calendar_proof.png`: solicitud de creación del evento desde Telegram.
- `Google_Calendar_proof.png`: evento creado en Google Calendar.

## Conclusión
Se ha implementado y validado satisfactoriamente el flujo completo de integración:

Telegram → OpenClaw → Zapier MCP → Google Workspace

Las pruebas realizadas confirman que el agente puede ejecutar acciones sobre aplicaciones externas mediante instrucciones en lenguaje natural, incluyendo la creación de documentos, la programación de eventos y el envío de invitaciones.

La solución se encuentra desplegada en un servidor VPS, lo que permite su funcionamiento independiente del ordenador local.