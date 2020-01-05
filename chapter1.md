---
title: 'Condicionales y control de flujo'
description: 'En este capítulo, aprenderás a usar operadores relacionales para comparar objetos en R, y operadores lógicos como "y" y "o" para combinar valores TRUE y FALSE. Además, usarás este conocimiento para construir enunciados condicionales.'
---

## Igualdad

```yaml
type: NormalExercise
key: 79c081df2a
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->
La forma más básica de comparación es la igualdad. Recapitulemos brevemente su sintaxis. Los siguientes enunciados evalúan a TRUE (Siéntete libre de probarlo en la consola).

```
3 == (2 + 1)
"intermediate" != "r"
TRUE != FALSE
"Rchitect" != "rchitect"
```
Observa que en la última expresión R es sensible a mayúsculas: "R" no es igual a "r". ¡Ten esto en mente al resolver ejercicios en este capítulo!

`@instructions`
<!-- Guidelines for instructions https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->
- En el editor de la derecha, escribe código R para ver si `TRUE` es igual a `FALSE`.
- Igualmente, revisa si `-6 * 14` es diferente a `17 - 101`.
- Siguiente: Comparación de cadenas de caracteres. Consulta en R si las cadenas "useR" y "user" son iguales.
- Finalmente, averigua qué pasa si comparas valores lógicos con numéricos: ¿son `TRUE` y 1 iguales?

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
En la última instrucción, no necesitas ningún paso adicional para hacer la comparación; solo utiliza los mismos operadores que en los anteriores.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Comparación de valores lógicos


# Comparación de valores numéricos


# Comparación de cadenas de caracteres


# Comparación de valor lógico con numérico

```

`@solution`
```{r}
# Comparación de valores lógicos
TRUE == FALSE

# Comparación de valores numéricos
-6 * 14 != 17 - 101

# Comparación de cadenas de caracteres
"useR" == "user"

# Comparación de valor lógico con numérico
TRUE == 1
```

`@sct`
```{r}
# Examples of good success messages: https://instructor-support.datacamp.com/en/articles/2299773-exercise-success-messages.
ex() %>% 
check_code(
  c("TRUE ?== ?FALSE", "T ?== ?F"), 
  missing_msg = "Fijate de nuevo en la comparación de valores lógicos. Deberías usar `TRUE == ___`; ¿puedes reemplazar el `___`?",
drop_comments = TRUE)

ex() %>% 
check_code(
  	"-6 ?\\* ?14 ?!= ?17 ?- ?101",
	missing_msg = "Dale otra mirada a la comparación de valores numéricos (segunda instrucción). Deberías usar `-6 * 14 != ___ - ___`, ¿puedes rellenar las partes que faltan?",
drop_comments = TRUE)

ex() %>% 
check_code(
	'"useR" ?== ?"user"',
	missing_msg = 'Revisa tu código de comparación de cadenas de caracteres. Debes ver si `"useR"` y `"user"` son iguales (`==`)')

ex() %>% 
check_code(
    c("TRUE ?== ?1", "T ?== ?1"),
  	missing_msg = "¿Comparaste correctamente a `TRUE` con `1` usando el operador de igualdad (`==`)?"
)

success_msg("¡Asombroso!, Dado que `TRUE` se coerce a `1` tras bambalinas, `TRUE == 1` se evalúa a `TRUE`. Asegúrate de no confundir `==` (comparación) y `=` (asignamiento), `==` es el que se necesita para verificar la igualdad de objetos en R.")
```
