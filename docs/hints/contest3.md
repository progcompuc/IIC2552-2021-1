---
title: contest 3 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```

### D - Update the array!
<details> 
  <summary>Hint</summary>
  Podemos construir un arreglo D de que guarde las diferencias que generan los updates, en otras palabras, si se hace un update l, r, v, realizamos D[l] += v, D[r + 1] -= v. Luego pensar en una forma de rescatar el valor en un índice de forma rápida, luego de los updates y usando el arreglo D.
</details>
<details> 
  <summary>Solución + código</summary>
  Una forma de resolver este problema de forma online, podemos hacer uso del arreglo de diferencias descrito en el hint y generar un segment tree de el que calcule la suma en un rango. Luego se recupera el valor en un índice realizando queries de la forma (0, i) a la estructura.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/UpdateTheArray.cpp">Código de ejemplo</a>
</details>

### E - Range Minimum Query
<details> 
  <summary>Hint</summary>
  Problema de uso directo de alguna de las estructuras vistas en clases
</details>
<details> 
  <summary>Solución + código</summary>
  Puede ser resuelto con uso directo de Segment Tree o Sparse Tables.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/RangeMinimumQuery.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```
