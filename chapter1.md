---
title: 'Condicionales y control de flujo'
description: 'En este capítulo, aprenderás a usar operadores relacionales para comparar objetos en R, y operadores lógicos como "y" y "o" para combinar valores TRUE y FALSE. Además, usarás este conocimiento para construir enunciados condicionales.'
---

## Operadores Relacionales

```yaml
type: VideoExercise
key: 84f225c714
xp: 50
```

`@projector_key`
d2e4404e3912c58ee0a6f7fd065cd92c

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
    	c("TRUE ?> ?FALSE", "T ?> ?F"),
      missing_msg = "La comparación de valores lógicos no es correcta. `TRUE > ___` es parte de la solución, te toca llenar los `___`. ¡Inténtalo otra vez!")

success_msg("¡Bien hecho! Asegúrate de darle una mirada a la consola para ver si R devuelve los resultados que esperas.")

```

---

## Comparar vectores

```yaml
type: NormalExercise
key: fee9b5eafc
xp: 100
```

Ya estás al tanto de que R es muy bueno con vectores. Sin tener que cambiar nada en la sintaxis, los operadores relacionales de R también trabajan con vectores.

Retornemos al ejemplo que empezó en el vídeo. Quieres determinar si tu actividad en redes sociales han dado frutos y decides revisar tus resultados para LinkedIn y Facebook. El código de muestra en tu editor de script inicializa los vectores `linkedin` y `facebook`. Cada uno de los vectores contiene el número de vistas que tus perfiles de LinkedIn y Facebook han tenido en los últimos siete días.

`@instructions`
Usando operadores relacionales, obtén un resultado lógico, es decir `TRUE` o `FALSE`, para las siguientes preguntas:

- ¿En qué días el número de vistas al perfil de LinkedIn superó las 15?
- ¿En qué días tu perfil de LinkedIn sólo fue visto 5 veces o menos?
- ¿En qué días tu perfil de LinkedIn fue más visitado que tu perfil de Facebook?

`@hint`
Vamos a ayudarte con un ejemplo de comparación. Para ver qué días tu perfil de LinkedIn fue visto más de 10 veces utiliza
```
linkedin > 10
```

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Los vectores linkedin y facebook ya han sido creados para ti
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)

# Días populares


# Días silenciosos


# Días en que LinkedIn fue más visitado que Facebook

```

`@solution`
```{r}
# Los vectores linkedin y facebook ya han sido creados para ti
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)

# Días populares
linkedin > 15

# Días silenciosos
linkedin <= 5

# Días en que LinkedIn fue más visitado que Facebook
linkedin > facebook
```

`@sct`
```{r}
ex() %>% 
	check_code(
    			"linkedin ?> ?15",
    			missing_msg = "Revisa tu código para encontrar días populares en LinkedIn. Puedes usar `> 15` para ello. Simplemente imprime el resultado")

ex() %>% 
	check_code(
    			"linkedin ?<= ?5",
    			missing_msg = "Revisa tu código para encontrar días silenciosos en LinkedIn. Puedes usar `<= 5` para ello. Asegúrate de usar el operador relacional adecuado e imprime el resultado.")

ex() %>% 
	check_code(
    			"linkedin ?> ?facebook",
    			missing_msg = "¿Resolviste correctamente la última instrucción? Simplemente combina `linkedin` y `facebook` con `>` para así obtener `TRUE` o `FALSE` para cada día; `TRUE` si tu perfil de LinkedIn obtuvo más visitas que tu perfil de Facebook ese día, y `FALSE` si no fue así. Simplemente imprime el resultado.")

success_msg("¡Maravilloso! Dale una mirada a output de la consola, tu perfil de LinkedIn fue bastante popular en el sexto día, pero menos popular en el cuarto y quinto día.")
```

---

## Comparar matrices

```yaml
type: NormalExercise
key: 63bce01e4c
xp: 100
```

La habilidad de trabajar con diferentes tipo de estructuras de datos que tiene R no se termina con los vectores. ¡Las matrices y los operadores relacionales también trabajan juntas perfectamente!

En lugar de vectores (como en el ejercicio anterior), los datos de LinkedIn y Facebook ahora están registrados en una matriz llamada `views`. La primera fila contiene la información de LinkedIn; la segunda tiene la información de Facebook. Los vectores originales `facebook` y `linkedin` también siguen disponibles.

`@instructions`
Usando los operadores relacionales que has aprendido hasta ahora, intenta descubrir lo siguiente: 

- ¿Cuándo fue que las visitas fueron exactamente iguales a 13? Usa la matriz `views` para retornar una matriz de valores lógicos.
- ¿En qué días el número de visitas fue menor o igual a 14? Nuevamente, haz que R retorne una matriz lógica.

`@hint`
Para ver qué días las vistas fueron igual a 13, puedes usar el operador `==`, ¡tal y como hiciste con los vectores!

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# La data ha sido creada para ti
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)
views <- matrix(c(linkedin, facebook), nrow = 2, byrow = TRUE)

# ¿En qué diás las visitas son igual a 13?


# ¿Cuándo fueron igual o menor que 14 las visitas?

```

`@solution`
```{r}
# La data ha sido creada para ti
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)
views <- matrix(c(linkedin, facebook), nrow = 2, byrow = TRUE)

# ¿En qué diás las visitas son igual a 13?
views == 13

# ¿Cuándo fueron igual o menor que 14 las visitas?
views <= 14
```

`@sct`
```{r}
ex() %>% 
	check_code(
    			"views ?== ?13",
    			missing_msg = "Dale otra mirada al código que calcula cuándo la matriz `views` equivale a 13. Puedes usar `views == 13`. Asegúrate de imprimir el resultado.")

ex() %>% 
	check_code(
    			"views <= 14",
    			missing_msg = "Dale otra mirada a la segunda instrucción. ¿Estás usando el operador `<=`? Simplemente imprime el resultado.")

success_msg("¡Buen trabajo! Con este ejercicio concluye la parte de comparadores. Ahora que saber consultar la reación entre objetos en R, el siguiente paso será usar los resultados para alterar el comportamiento de tus programas. ¡Descúbre todo acerca de ello en el siguiente vídeo!")

```

---

## Operadores Lógicos

```yaml
type: VideoExercise
key: c6bb44ca7f
xp: 50
```

`@projector_key`
14148a7d67fc4a10dc5c5b94afdc3676
