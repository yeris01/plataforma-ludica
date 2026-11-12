# Mini-aplicación de práctica: [tema] 
 
## Versión A 
 
**Objetivo:** construir la mini-aplicación con un prompt de una línea. 
**Herramienta y modelo:** Copilot con el modelo [modelo]. 
**Prompt:** [prompt exacto, dentro de un bloque de código] 
**Resultado:** [qué produjo, pruebas aprobadas X de N y errores de Ruff] 
 
## Versión B 
 
**Objetivo:** construir la misma aplicación con un prompt estructurado, AGENTS.md y 
pruebas de aceptación. 
**Herramienta y modelo:** Copilot con el modelo [modelo]. 
**Prompt:** [prompt exacto, dentro de un bloque de código] 
**Resultado:** [qué produjo, cuántos intentos necesitó, pruebas aprobadas X de N y 
errores de Ruff] 
 
## Mejora 
 
**Objetivo:** [la mejora del anexo, en una frase]. 
**Herramienta y modelo:** Copilot con el modelo [modelo]. 
**Prompt:** [prompt exacto, dentro de un bloque de código] 
**Resultado:** [qué produjo y qué hubo que corregir] 
 
## Comparación 
 
[Pruebas aprobadas, requisitos cumplidos y errores de Ruff de cada versión, y la 
conclusión de la actividad 4.]# Plantilla de prompt

## Rol
Actúa como [perfil del experto que se necesita].

## Objetivo
[Qué se debe construir o resolver, en una o dos frases, con los datos exactos: rutas, campos y respuestas.]

## Contexto
Lee AGENTS.md. [Archivos que debe leer y para qué.]

## Restricciones
- [Lo que no puede hacer o usar.]
- No modifiques las pruebas existentes.

## Formato de salida
Antes de escribir código, muestra el plan con las rutas completas de los archivos y espera mi aprobación.

## Ejemplo
[Una entrada y la salida esperada.]

## Criterio de éxito
[El comando que comprueba que terminó, por ejemplo pytest -v sin pruebas fallidas.]
Si después de 3 intentos no se cumple, detente y explica el problema.
