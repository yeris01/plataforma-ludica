## Objetivo

Agregar el endpoint `GET /api/version` con su prueba en `tests/test_inicio.py`.

## Herramienta y modelo

Copilot en VS Code, modo Interactive y permisos Manual. El modelo no quedó indicado.

## Prompt

Lee AGENTS.md. Agrega el endpoint GET /api/version, que devuelva la versión definida
en app/proyecto.py, con su prueba en tests/test_inicio.py. Antes de escribir código,
explícame qué archivos vas a modificar y espera mi aprobación.

## Resultado

El agente agregó la ruta en `app/rutas/api.py` y una prueba en `tests/test_inicio.py`
que verifica el código HTTP y que la versión coincide con `proyecto.VERSION`. La
prueba del endpoint pasó. En esta copia del repositorio, `/salud` ya respondía
`{"estado": "ok"}` y no fue necesario modificar esa ruta. Las verificaciones
completas se ejecutaron después de preparar la rama.
