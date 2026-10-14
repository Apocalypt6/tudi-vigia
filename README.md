# Vigía externo de Tudi

Este repo revisa desde GitHub (fuera de nuestro servidor) que Tudi esté arriba. Solo contiene URLs públicas; no guarda secretos.

- Cada 5 minutos revisa `tudiapp.co/` y `tudiapp.co/panel/` (200), `appdeuna.com/healthz` y `/readyz` (200) y `appdeuna.com/api/panel` (401 sin sesión).
- Cada URL se prueba hasta 3 veces (2 reintentos, 15 s entre intentos, 20 s de tope por intento).
- Si alguna falla, la corrida termina en rojo y GitHub avisa al dueño del repo por correo y por la app GitHub Mobile ("failed workflows"). No abre issues, para que una caída no quede pública.
- `latido.yml` escribe `ultimo-latido.txt` el día 1 de cada mes: GitHub desactiva los workflows programados de un repo público tras 60 días sin actividad, y este commit lo evita.
- Prueba manual: pestaña Actions, "Vigia", Run workflow.
