---
title: 'Chapter Title Here'
description: 'Chapter description goes here.'
---

## Ejercicio de ejemplo

```yaml
type: NormalExercise
key: 2bafef99a3
lang: r
xp: 100
skills: 1
```

Este es un ejemplo de ejercicio utilizando ggplot2

`@instructions`
1. Crea un diagrama de dispersión de mtcars. Ya se realizó el llamado a ggplot2

`@hint`
Usa las variables mpg y wt para realizarlo

`@pre_exercise_code`
```{r}
library(ggplot2)
```

`@sample_code`
```{r}
# Reemplaza los espacios en blanco
ggplot(___, aes(___, ___)) +
geom_point()
```

`@solution`
```{r}
ggplot(mtcars, aes(mpg, wt)) +
geom_point()
```

`@sct`
```{r}

```

---

## Insert exercise title here

```yaml
type: VideoExercise
key: 4da74b5ebf
xp: 50
```

`@projector_key`
ba45f76f595566ae8d3ff65cbb3d9dea
