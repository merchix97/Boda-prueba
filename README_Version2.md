# Servidor RSVP (Boda Mer & Luis)

Esta pequeña app recibe POST /rsvp desde el formulario y envía un correo con los datos a la dirección indicada.

## Archivos incluidos
- index.html — formulario + JS cliente (modifica ENDPOINT si el servidor está en otro dominio).
- server.js — servidor Express + nodemailer.
- package.json
- .env.example

## Variables de entorno (ejemplo en .env)
- SMTP_HOST=smtp.gmail.com
- SMTP_PORT=587
- SMTP_SECURE=false
- SMTP_USER=tu_usuario_smtp
- SMTP_PASS=tu_contraseña_smtp_o_app_password
- FROM_EMAIL=opcional@tudominio.com
- TO_EMAIL=meryubero14@gmail.com

Nota: para Gmail necesita configurar un App Password si tienes 2FA (no uses la contraseña normal en producción si no tienes 2FA). También puedes usar SendGrid, Mailgun u otro servicio SMTP.

## Ejecutar localmente
1. Instala dependencias:
   npm install
2. Crea un fichero .env con las variables (o exporta las variables).
3. Ejecuta:
   npm start
4. Si index.html está en el mismo servidor (mismo host), deja ENDPOINT = '' en el script. Si sirves el frontend en otro host, pon la URL completa en API_BASE.

## Despliegue
Puedes desplegarlo en servicios como Render, Railway, Heroku o Vercel (serverless con adaptaciones). Asegúrate de configurar las variables de entorno en el panel del servicio.

## Seguridad y privacidad
- El honeypot `website` ayuda a bloquear bots; no confíes solo en ello.
- No expongas credenciales SMTP en repositorios públicos.
- Solo usa los datos para la finalidad indicada y cumple con la normativa de protección de datos aplicable.