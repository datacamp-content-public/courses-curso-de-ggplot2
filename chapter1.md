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

---

## Mayor que y menor que

```yaml
type: NormalExercise
key: bee63a594d
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->
Además del operador de igualdad, Filip nos presentó los operadores *menor que* y *mayor que*: `<` y `>`. También puedes agregar un signo de igual para expresar *menor o igual que* o *mayor o igual que*, respectivamente. Dale una mirada a las siguientes expresiones en R, todas se evalúan a `FALSE`:
```
(1 + 2) > 4
"dog" < "Cats"
TRUE <= FALSE
```
Recuerda que para comparación de cadenas, R determina la relación *mayor que* basado en el orden alfabético. También, ten en mente que `TRUE` es tratado como `1` por razones aritméticas, y `FALSE` es tratado como `0`. Por lo tanto, `FALSE < TRUE` es `TRUE`.

`@instructions`
<!-- Guidelines for instructions https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->
Escribe expresiones en R para verificar si:
- `-6 * 5 + 2` es mayor o igual que `-10 +1`
- "raining" es menor o igual que "raining dogs"
- `TRUE` es mayor que `FALSE`

`@hint`
La respuesta correcta a la segunda instrucción sería:

```
"raining" <= "raining dogs"
```

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Comparación de valores numéricos


# Comparison de cadenas de caracteres


# Comparación de valores lógicos

```

`@solution`
```{r}
# Comparación de valores numéricos
-6 * 5 + 2 >= -10 + 1

# Comparison de cadenas de caracteres
"raining" <= "raining dogs"

# Comparación de valores lógicos
TRUE > FALSE
```

`@sct`
```{r}
ex() %>% 
	check_code(
    	"- ?6 \\* ?5 ?\\+ ?2 ?>= ?-10 ?\\+ ?1",
    missing_msg = "Dale otra mirada a la comparación de numéricos en tu script. Deberías usar algo como `-6 * 5 + 2 >= ___`; ¿puedes llenar lo que falta'")

ex() %>% 
	check_code(
    	'"raining" ?<= ?"raining dogs"',
    	missing_msg = 'Hay un error en la comparación de cadenas de caracteres. Deberías usar algo como `"raining" <= ___`; ¿puedes llenar lo que falta?')

ex() %>% 
	check_code(
    	c("TRUE ?> F?ALSE", "T ?> ? F"),
      missing_msg = "La comparación de valores lógicos no es correcta. `TRUE > ___` es parte de la solución, te toca llenar los `___`. ¡Inténtalo otra vez!")

success_msg("¡Bien hecho! Asegúrate de darle una mirada a la consola para ver si R devuelve los resultados que esperas.")

```
