# Flybots - Chatbot Web para Bares y Restaurantes (SaaS)

Chat web interactivo para pedidos en mesa, pensado para escanear un QR y abrir un chat conectado a n8n. Ideal para bares, restaurantes y cafeterías que quieren digitalizar la experiencia de atención al cliente.

---

## 🚀 ¿Qué es Flybots?

- **Interfaz web tipo WhatsApp**: El cliente escanea un QR en la mesa y accede a un chat sencillo y directo.
- **Respuestas automáticas**: Un agente virtual (IA vía n8n/OpenAI) responde y gestiona pedidos.
- **Menú dinámico**: Integración con Google Sheets para mostrar productos y precios en tiempo real.
- **Notificaciones al staff**: Los pedidos confirmados se envían automáticamente a Telegram o cualquier canal soportado por n8n.
- **Multi-idioma**: Preparado para español, gallego y fácil de ampliar.
- **Fácilmente personalizable**: Branding, colores y textos adaptables.

---

## 🛠️ Mejoras implementadas respecto a la versión original

- Código modular y limpio (separación de lógica de UI, API y utilidades).
- Configuración del endpoint de n8n por variable (no hardcodeado).
- Mejor manejo de errores y feedback al usuario.
- Preparado para internacionalización y personalización.
- Comentarios y estructura lista para escalar.

---

## 💡 ¿Por qué migrar a un framework (React, Vue, Svelte)?

- **Escalabilidad**: Frameworks permiten manejar componentes complejos, estados y rutas de forma más robusta.
- **Mantenibilidad**: Mejor organización del código, pruebas y colaboración en equipo.
- **Integraciones**: Más fácil añadir autenticación, dashboards, analíticas, etc.
- **Performance**: Mejor gestión del DOM y optimización para apps grandes.
- **Ecosistema**: Acceso a librerías modernas y soporte de la comunidad.

*Para MVP y prototipos, vanilla JS es suficiente. Para SaaS serio y multi-cliente, migrar a un framework es recomendable.*

---

## 🏪 ¿Por qué Flybots es ideal para tu negocio?

- Digitaliza la atención sin apps ni instalaciones.
- Reduce errores y tiempos de espera.
- Mejora la experiencia del cliente.
- Fácil de desplegar y personalizar para cada local.

---

## 🔗 ¿Cómo funciona?

1. El cliente escanea un QR en la mesa.
2. Se abre una web con el chat.
3. El cliente escribe su pedido.
4. El mensaje llega a n8n, que lo procesa y responde.
5. El staff recibe el pedido por Telegram o similar.

---

## ⚙️ Instalación y despliegue

1. Clona este repositorio:
   ```bash
   git clone https://github.com/DavidIL02/flybots.git
   cd flybots
   ```
2. Abre `index.html` en tu navegador para pruebas locales.
3. Configura tu endpoint de n8n en el código o como variable global JS.
4. Despliega en Netlify, Vercel o cualquier hosting estático.

---

## 🔒 Seguridad y privacidad

- No se almacena información personal del cliente en el frontend.
- Toda la lógica sensible se gestiona en n8n (backend).
- Recomendado usar HTTPS y dominios propios en producción.

---

## ✨ Mejoras futuras sugeridas

- [ ] Migrar a framework moderno para escalabilidad.
- [ ] Añadir grabación/envío de audio.
- [ ] Panel de administración para el local.
- [ ] Analíticas de uso y satisfacción.
- [ ] Integración con sistemas de pago.

---

## 📞 Contacto y soporte

¿Quieres una demo o soporte? Contáctanos vía GitHub o email.

---

## Licencia

MIT
