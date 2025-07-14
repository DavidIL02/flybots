# Chatbotbar - Explicación Técnica y Guía de Desarrollo

## 1. Estructura del Proyecto

- `index.html`: Interfaz principal del chat, minimalista y responsive, simulando WhatsApp.
- `script.js`: Lógica de frontend. Maneja mensajes, integración con backend (n8n), animaciones y UX.
- `style.css`: Estilos modernos, mobile-first, con detalles visuales tipo app de mensajería.
- `ChatBot.json`: Configuración del bot (no siempre necesario para pruebas locales).
- `README.md`: Documentación original.

## 2. Flujo de Funcionamiento

### Frontend
- Al abrir `index.html`, se muestra un chat con bienvenida personalizada (detecta el número de mesa por query string: `?mesa=7`).
- El usuario escribe un mensaje. Al enviar:
  - Se muestra el mensaje en pantalla.
  - Aparece una animación de "..." (bot escribiendo).
  - Se hace un POST a la URL del backend (por defecto: `http://192.168.1.42:5678/webhook/chatbot`), enviando `{ message, mesa }`.
  - Al recibir respuesta, se muestra el mensaje del bot y se elimina la animación.
  - Si hay error de red, se notifica al usuario.

### Backend (n8n)
- El endpoint espera `{ message, mesa }`.
- El flujo de n8n puede:
  - Consultar Google Sheets para obtener el menú en tiempo real.
  - Usar OpenAI para generar respuestas personalizadas.
  - Confirmar pedidos y notificar por Telegram.
- El menú es editable en Google Sheets y se refleja en tiempo real.

## 3. Personalización y Extensión

- **Cambiar endpoint backend:**
  - Edita la URL en `script.js` (línea con `fetch(...)`).
- **Apariencia:**
  - Modifica `style.css` para adaptar colores, fuentes, burbujas, etc.
- **Mensajes de bienvenida:**
  - Personaliza el bloque de bienvenida en `script.js` (evento `DOMContentLoaded`).
- **Animación de "...":**
  - Controlada por las funciones `showTypingIndicator` y `removeTypingIndicator`.
- **Soporte multi-idioma:**
  - El frontend soporta español y gallego. El backend puede extenderse para más idiomas.
- **Funcionalidad de audio:**
  - El código está preparado para añadir grabación/envío de voz (ver roadmap en README.md).

## 4. Ejemplo de Integración Local

1. Clona el repo y abre `index.html` en tu navegador.
2. Para simular una mesa: `index.html?mesa=7`.
3. Asegúrate de tener n8n corriendo y el endpoint configurado.
4. Edita Google Sheets para modificar el menú en tiempo real.

## 5. Roadmap y Mejoras
- Desplegar n8n en un servidor accesible públicamente.
- Añadir grabación/envío de mensajes de voz.
- Unificar todo bajo un dominio propio.
- Mejorar fallback y UX para errores de red.

## 6. Tips para Devs
- El código es simple y directo, ideal para prototipado rápido.
- Puedes migrar fácilmente a frameworks modernos (React, Vue) si necesitas más escalabilidad.
- El flujo n8n es el core de la lógica de negocio: puedes extenderlo para pagos, reservas, etc.

---

¿Dudas o quieres extender el sistema? Solo edita el JS/CSS o el flujo de n8n. El frontend es 100% estático y desacoplado del backend. 