# n8n-Lead-Capture-Onboarding-Workflow-Google-Forms-HubSpot-Gmail-Slack-


Workflow n8n: Google Forms → Validación de email → HubSpot → Email → Slack

Este workflow automatiza la gestión de leads capturados desde un formulario de Google Forms.
Valida el correo recibido, crea o actualiza el contacto en HubSpot, envía un correo de bienvenida y notifica al equipo por Slack.
Si el correo no cumple la validación, envía un aviso de error en Slack para seguimiento manual.

Flujo general

1. Google Forms → Webhook
El formulario envía las respuestas a n8n mediante un webhook.

2. Normalización de datos
Se organizan los campos recibidos (nombre, email, teléfono, etc.).

3. Validación del email
Se aplica una condición específica para determinar si el correo continúa en el flujo.

4. Si el correo es válido:

	Se crea o actualiza el contacto en HubSpot.

	Se envía un email de bienvenida.

	Se notifica en Slack la creación del contacto.

5. Si el correo es inválido:

	Se envía una alerta en Slack informando que el contacto debe revisarse manualmente.


Requisitos

	Instancia de n8n.

	Credenciales configuradas para HubSpot, Slack, email (Gmail/SMTP) y Google si aplicara.

	Webhook público generado desde n8n.


Importación del workflow

1. En n8n: Workflows → Import → Load File.

2. Selecciona el archivo JSON.

3. Configura las credenciales en los nodos.

4. Activa el webhook y copia su URL.


Cómo probar el flujo

1. Crea un Google Form con los campos necesarios.

2. Conéctalo al webhook de n8n usando un script, un conector o una automatización que envíe las respuestas a la URL del webhook.

3. Envía una respuesta del formulario.

4. Verifica:

	Que el workflow se active en n8n.

	Que se aplique la validación del correo.

	Que se envíen las notificaciones y acciones según corresponda.
