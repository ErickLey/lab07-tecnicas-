# Bitacora de tecnicas avanzadas 
 
Laboratorio 07: Tecnicas Avanzadas de Prompting. 
Herramienta de IA usada: (escribe aqui cual usaste) 
 
## Ejercicio 2: Zero-shot, one-shot y few-shot 
 | Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|---|---|---|---|
| Zero-shot | 5 | Tabla con columnas Comentario y Clasificación | No |
| One-shot | 5 | Lista numerada con texto libre y flecha | No |
| Few-shot | 5 | Texto exacto con comillas, flecha y clasificación | Si |
## Ejercicio 3: Chain of Thought 
 | Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|---|---|---|---|
| Directo | 318.60 | No | Si |
| Paso a paso | Muestra cálculos por unidad y total | Si | Si |

Ver el razonamiento es útil porque permite encontrar exactamente dónde se equivocó la IA si la respuesta final es incorrecta, en lugar de solo tener un número sin justificación.

## Ejercicio 4: Role prompting

| Versión | Vocabulario (sencillo/técnico) | Usa ejemplos o código | A quién le sirve |
|---|---|---|---|
| B. Rol docente | Sencillo y cotidiano | Ejemplos: caja de zapatos, monedas de juego | Estudiantes sin experiencia |
| C. Rol senior | Técnico (RAM, fuertemente tipado) | Código Java avanzado, conceptos de JVM | Compañeros desarrolladores |

## Ejercicio 5: Descomposicion

* **Paso 1:** Entregó una lista de 5 requisitos funcionales para el sistema.
* **Paso 2:** Diseñó las clases (ej. Producto, Inventario) con sus atributos y tipos de datos.
* **Paso 3:** Generó el código exacto de la clase Producto con constructor, getters y setters.
* **Paso 4:** Propuso 3 mejoras de código sobre la clase recién creada.
* **Comparación:** El pedido paso a paso generó un código coherente y bien estructurado basado en los requisitos previos, mientras que un pedido directo genera una respuesta genérica.

## Ejercicio 6: Prompt estructurado y autocritica

| Qué revisar | Cumple (Sí / No) |
|---|---|
| ¿Tiene las 4 columnas pedidas? | Sí |
| ¿Incluye el bloqueo después de 3 intentos? | Sí |
| ¿Incluye casos con campos vacíos? | Sí |
| ¿Indica qué casos agregó en la autocrítica? | Sí |
| ¿Hay algún caso repetido o que no tenga sentido? | No |

```text
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>

Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.