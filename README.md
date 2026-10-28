# VolleyWorld — tareas programadas

Este repositorio no contiene código de la aplicación. Solo guarda tareas
programadas de GitHub Actions (`.github/workflows/`):

- `ping.yml`: una petición ligera a `https://volley-world-app.onrender.com/api/health`
  cada 10 minutos. El plan gratuito de Render "duerme" el servidor tras 15
  minutos sin visitas y la primera persona que entra después espera 30-60
  segundos mientras se despierta; con este ping se reducen esas esperas
  (GitHub no garantiza la hora exacta de las tareas programadas, así que no
  las evita del todo).
- `tareas-periodicas.yml`: una llamada programada a la aplicación cada 2
  horas. Su dirección y su clave de acceso están en los secretos del
  repositorio (`SCHEDULER_URL` y `CRON_HEADER`).
- `mantenimiento.yml`: una vez a la semana comprueba el último commit y, si
  tiene más de 30 días, añade uno vacío. GitHub desactiva las tareas
  programadas de un repositorio público tras 60 días sin actividad, y esto
  evita que vuelva a pasar.

Es un repositorio público a propósito: GitHub da minutos de Actions
ilimitados a los repositorios públicos, así estas tareas no consumen el cupo
gratuito de los repositorios privados de la cuenta. Por eso mismo no debe
guardarse aquí nada sensible: las claves van siempre en los secretos.
