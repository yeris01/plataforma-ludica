# STATE.md

Estado del proyecto. Léalo al iniciar cada sesión de trabajo y actualícelo al cerrarla.

## Estado actual

Aplicación publicada en Render: https://plataforma-ludica-j1ux.onrender.com/.
La página de inicio, /salud, /docs y /api/version responden correctamente. El
endpoint /api/version devuelve {"version":"0.1.0"}. GitHub Actions está
configurado para revisar el estilo, ejecutar las pruebas y comprobar el arranque.

## Decisiones

| Fecha | Decisión | Motivo |
| --- | --- | --- |
| 2026-11-10 | Usar FastAPI para la aplicación web | Es el stack definido para el proyecto |
| 2026-11-10 | Exponer GET /api/version con la versión de app/proyecto.py | Permite consultar la versión desplegada; responde con el formato {"version": "..."} |

## Siguiente paso

Completar `specs/spec.md` con historias de usuario y criterios de aceptación concretos para los roles docente y niño.
