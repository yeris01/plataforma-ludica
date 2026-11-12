# Mini-aplicación de práctica: Conversor de unidades

## Versión A

**Objetivo:** construir la mini-aplicación con un prompt de una línea.  
**Herramienta y modelo:** Copilot; el modelo no quedó registrado.  
**Prompt:** No se encontró el texto literal del prompt A en los archivos disponibles ni en la conversación consultada.

**Resultado:** produjo un conversor de unidades con API e interfaz web. La suite ejecutada aprobó 14 de 14 pruebas y Ruff no reportó errores.

## Versión B

**Objetivo:** construir la misma aplicación con un prompt estructurado, AGENTS.md y pruebas de aceptación.  
**Herramienta y modelo:** Copilot; el modelo no quedó registrado.  
**Prompt:**

````
## Rol
Actúa como desarrollador backend con experiencia en FastAPI, Jinja2 y pruebas con
pytest.

## Objetivo
Construir la mini-aplicación web **Conversor de unidades** con estos requisitos:
- Crear una aplicación web en español que permita convertir valores entre unidades.
- Incluir las categorías longitud, masa, temperatura, volumen, superficie, tiempo,
  velocidad y datos.
- Implementar `GET /api/units` para devolver las ocho categorías, sus etiquetas,
  símbolos y unidades con código y nombre.
- Implementar `POST /api/convert` para convertir entre dos unidades de la misma
  categoría. La solicitud debe aceptar `category`, `value`, `from_unit` y `to_unit`;
  la respuesta debe incluir el valor recibido, el resultado y los códigos de unidades.
- Convertir correctamente longitud y temperatura; rechazar categorías o unidades
  inválidas, valores no finitos y resultados fuera de rango con código HTTP 422.
- Servir la página principal en `/` y los estilos en `/static/styles.css`.
- Crear una interfaz que permita escoger categoría, valor y unidades, enviar la
  conversión y mostrar el resultado o un mensaje de error.

## Contexto
Lee AGENTS.md. El contrato de la API está en tests/test_aceptacion.py: las rutas, los
nombres de los campos y los códigos de estado deben coincidir con esas pruebas.

## Restricciones
- Usa solo las dependencias de requirements.txt.
- Define las rutas en app/main.py y la lógica en app/servicios.py, sin importar
  FastAPI en servicios.
- Guarda los datos en memoria, sin base de datos ni archivos.
- No modifiques tests/test_aceptacion.py.
- La página usa HTML, CSS y JavaScript sin librerías externas.

## Formato de salida
Antes de escribir código, muestra el plan con las rutas completas de los archivos que
vas a crear y espera mi aprobación. Al terminar, resume en una línea qué hace cada
archivo.

## Ejemplo
Solicitud para convertir 1 kilómetro a millas:

```json
{
  "category": "longitud",
  "value": 1,
  "from_unit": "km",
  "to_unit": "mi"
}
```

## Criterio de éxito
`python -m pytest -v` pasa todas las pruebas y `ruff check .` no reporta errores. Si
después de 3 intentos las pruebas no pasan, detente y explica el problema.
````

**Resultado:** implementó el conversor y la mejora de consulta de tareas pendientes. La verificación de aceptación y mejora aprobó 10 de 10 pruebas; Ruff no reportó errores. El número de intentos de implementación no quedó registrado.

## Mejora

**Objetivo:** agregar un endpoint para consultar las tareas pendientes y permitir que el usuario las vea desde la página principal, conservando el conversor existente.  
**Herramienta y modelo:** Copilot; el modelo no quedó registrado.  
**Prompt:**

````
No inventes rutas, parámetros, respuestas ni comportamientos que no estén
especificados a continuación o en el proyecto.

## Rol
Actúa como desarrollador backend con experiencia en FastAPI, Jinja2 y pruebas con
pytest.

## Objetivo
Mejorar la aplicación implementando exactamente la funcionalidad descrita en el anexo:

- Agregar un endpoint que devuelva las tareas pendientes.
- Método y ruta: `GET /api/tareas?estado=pendientes`.
- Parámetro de consulta: `estado=pendientes`.
- Respuesta de ejemplo: `[{"id": 2, "titulo": "Leer", "completada": false}]`.

Añade una prueba en `tests/test_mejora.py` que compruebe el endpoint y su respuesta.
Actualiza también la página principal para que el usuario pueda consultar y ver las
tareas pendientes.

## Contexto
Lee `AGENTS.md`, `app/servicios.py` y revisa la aplicación existente. La aplicación es
un conversor de unidades con `POST /api/convert`; conserva su comportamiento. El
contrato nuevo del anexo es `GET /api/tareas?estado=pendientes` y la respuesta de
ejemplo indicada en este prompt. Respeta literalmente la ruta, el parámetro y la
estructura de la respuesta. Si no está definido en el proyecto de dónde obtener las
tareas o qué devolver cuando no haya pendientes, solicita aclaración antes de cambiar
código; no inventes esos comportamientos.

## Restricciones
- No modifiques `tests/test_aceptacion.py`.
- Usa solo las dependencias de `requirements.txt`; no agregues dependencias.
- Mantén la lógica de negocio en `app/servicios.py`, sin importar FastAPI allí, y las
  rutas en `app/main.py`.
- La página principal debe permitir usar la mejora y mostrar su resultado.
- No implementes ningún comportamiento que no esté especificado en el anexo.
- Si falta información del contrato, detente y solicítala antes de cambiar código.

## Formato de salida
Antes de escribir código, muestra un plan con las rutas completas de todos los archivos
que crearás o modificarás, incluyendo `tests/test_mejora.py`. No uses enlaces.
Espera mi aprobación antes de hacer cambios. Al terminar, resume en una línea qué
cambió en cada archivo.

## Ejemplo
Petición exacta del anexo:

```http
GET /api/tareas?estado=pendientes
```

```json
[{"id": 2, "titulo": "Leer", "completada": false}]
```

## Criterio de éxito
Ejecuta `python -m pytest -v tests/test_aceptacion.py tests/test_mejora.py` y
`ruff check .`. Ambos comandos deben terminar sin fallos y `tests/test_aceptacion.py`
debe permanecer sin modificaciones. Si las pruebas fallan, realiza como máximo 3
intentos; después detente y explica el problema.
````

**Resultado:** agregó `GET /api/tareas?estado=pendientes`, tareas en memoria y un control en la página principal. La implementación devuelve objetos con `id`, `titulo` y `estado: "pendiente"`; esto no coincide literalmente con el ejemplo del prompt, que usa `completada: false`. Las pruebas de mejora existentes aprobaron, incluida la respuesta vacía cuando no hay tareas pendientes.

## Comparación

La Versión A aprobó 14 de 14 pruebas y Ruff no reportó errores. La Versión B y la mejora aprobaron 10 de 10 pruebas de aceptación y mejora; Ruff tampoco reportó errores. Ambas versiones conservaron un conversor funcional. La Versión B dejó documentada la estructura esperada, las restricciones y los criterios de aceptación; la mejora añadió la consulta de tareas. La respuesta real de tareas difiere del ejemplo de estructura del prompt, así que las pruebas aprobadas no acreditan que ese ejemplo se haya respetado literalmente. No se encontró una conclusión previa de la actividad 4; con los resultados disponibles, la especificación estructurada facilitó verificar los requisitos, aunque conviene alinear el contrato de la mejora con su respuesta de ejemplo.
