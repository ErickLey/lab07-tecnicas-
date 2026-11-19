# Tarea: Mi prompt avanzado

## Tarea elegida
Generar casos de prueba unitarios en Java (JUnit 5) para un método de validación de contraseñas seguras en un sistema de registro de usuarios.

## Version 1: prompt basico
```text
Escribe pruebas unitarias para validar una contraseña en Java.
# Tarea: Mi prompt avanzado

## Tarea elegida
Generar casos de prueba unitarios en Java (JUnit 5) para un método de validación de contraseñas seguras en un sistema de registro de usuarios.

## Version 1: prompt basico
```text
Escribe pruebas unitarias para validar una contraseña en Java.
```
* **Qué se agregó:** Ninguna técnica (prompt directo).
* **Por qué y qué mejoró:** Sirvió como línea base, pero la IA generó pruebas muy genéricas sin especificar la versión de JUnit ni cubrir casos límite reales.

## Version 2
```text
Actúa como un ingeniero de QA senior especialista en Java y JUnit 5. Escribe pruebas unitarias para validar un método `esContrasenaSegura(String password)` que exige mínimo 8 caracteres, una mayúscula, un número y un carácter especial. Piensa paso a paso qué escenarios pueden fallar antes de escribir el código.
```
* **Qué se agregó:** **Role prompting** (ingeniero de QA senior en Java/JUnit 5) y **Chain of Thought** ("piensa paso a paso qué escenarios pueden fallar").
* **Por qué y qué mejoró:** El rol ajustó el código a JUnit 5 moderno y el razonamiento paso a paso logró que la IA considerara escenarios negativos (contraseña muy corta, sin números) en lugar de probar solo el caso exitoso.

## Version 3: prompt final
```text
<rol>Actúa como un ingeniero de QA senior especialista en Java 17 y JUnit 5.</rol>
<contexto>Tenemos un método `boolean esContrasenaSegura(String password)` que retorna true solo si tiene mínimo 8 caracteres, al menos una mayúscula, un número y un símbolo especial (sin espacios).</contexto>
<tarea>
1. Piensa paso a paso todos los casos borde que pueden romper la validación.
2. Genera exactamente 6 métodos de prueba en JUnit 5 usando `@Test` y nombres descriptivos.
</tarea>
<formato>Primero muestra una tabla Markdown con las columnas: Caso, Entrada, Resultado Esperado. Luego entrega el bloque de código Java completo y listo para compilar.</formato>
```
* **Qué se agregó:** **Prompt estructurado** (etiquetas XML `<rol>`, `<contexto>`, `<tarea>`, `<formato>`) y **Descomposición** (dividiendo la salida en análisis de casos borde, tabla resumen y código final).
* **Por qué y qué mejoró:** Evitó que la IA mezclara explicaciones largas con el código, garantizó exactamente 6 pruebas limpias con casos límite (como espacios en blanco o cadenas vacías) y entregó tanto documentación tabular como código compilable.

## Tecnicas usadas en el prompt final

| Parte del prompt final | Técnica aplicada |
|---|---|
| `<rol>Actúa como un ingeniero de QA senior especialista en Java 17 y JUnit 5.</rol>` | Role prompting |
| `<rol>`, `<contexto>`, `<tarea>`, `<formato>` | Prompt estructurado |
| `1. Piensa paso a paso todos los casos borde...` | Chain of Thought |
| Dividir la tarea en: 1) análisis de borde, 2) tabla resumen y 3) código JUnit | Descomposición |

## Evaluacion del resultado

| Criterio | Cumple (Sí / No) |
|---|---|
| ¿Usa JUnit 5 (`@Test`) y sintaxis válida de Java? | Sí |
| ¿Incluye pruebas tanto para contraseñas válidas como inválidas? | Sí |
| ¿Cubre casos límite como cadenas vacías o espacios? | Sí |
| ¿Respeta el formato pedido (tabla + bloque de código)? | Sí |

## Por que elegi estas tecnicas
Elegí **Role prompting** porque generar pruebas unitarias requiere estándares técnicos específicos de JUnit 5 que un prompt sin rol suele omitir. Combiné **Prompt estructurado** y **Descomposición** porque al pedir tanto una tabla documental como código Java en una misma respuesta, separar las secciones con etiquetas evita que la IA mezcle texto con código o se olvide de algún requisito. Finalmente, agregué **Chain of Thought** para obligar al modelo a razonar los casos límite antes de programar, reduciendo pruebas repetidas o superficiales.