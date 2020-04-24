---
title: contest 6 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```

### F - Mixtures
<details> 
  <summary>Hint</summary>
  Podemos ver el problema desde el final del proceso hasta el principio, es decir, cual es el óptimo para las últimas 2 pociones que mezclemos? Sabemos que el humo que genera esta última mezcla sólo depende de los colores de las mezclas que contiene cada una, pero al poder juntarse sólo con adyacentes, necesariamente cada mezcla es la unión de un segmento contiguo de las pociones iniciales. Si pensamos el proceso de esta forma basta con tomar cada vez la opción que nos genere menos humo en generar estas "últimas pociones" y mezclarlas.
</details>
<details> 
  <summary>Solución + código</summary>
  Siguiendo lo expresado en el Hint, podemos hacer un DP sobre todos los segmentos contiguos de pociones iniciales, y para cada uno de estos el dp calcula el punto óptimo para unirlo, es decir cómo separar en 2 el segmento en cuestión de tal forma que si cada uno de los nuevos segmentos se mezcla de manera óptima, esta última mezcla genere la menor cantidad de humo (tomando en cuenta el humo óptimo de sus subsegmentos). Para calcular el humo de los subsegmentos basta ocupar la misma función dp sobre ellos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/Mixtures.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```
