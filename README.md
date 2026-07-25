# VolleyWorld — mantener el backend despierto

Este repositorio no tiene código de la aplicación — solo contiene una tarea
programada de GitHub Actions (`.github/workflows/keepalive.yml`) que hace una
petición ligera a `https://volley-world-app.onrender.com/api/health` cada 10
minutos.

**¿Por qué?** El plan gratuito de Render "duerme" el servidor tras 15 minutos
sin visitas, y la primera persona que entra después tiene que esperar 30-60
segundos mientras se despierta. Con esta tarea, el servidor nunca llega a
dormirse.

Es un repositorio público (no privado) a propósito: GitHub da minutos de
Actions ilimitados a los repositorios públicos, así esta tarea no consume el
cupo gratuito del repositorio privado de la app.
