---
title: contest 3 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```

### A - Ball
<details> 
  <summary>Hint 1</summary>
  Piensen un una forma de ordenar los datos tal que usando alguna estructura para cada persona podamos saber rápidamente si existe alguien que tenga todas las características mayores.
</details>
<details> 
  <summary>Hint 2</summary>
  Una posible idea es ordenar a las personas de forma decreciente en una de las características (por ejemplo B) e ir manteniendo en una estructura ordenadas según una segunda características (por ejemplo I) las terceras características (por ejemplo R). Piensen cómo mantener esto y en qué estructura ayudaría a saber si hay alguien dominante rápidamente.
</details>
<details> 
  <summary>Solución + código</summary>
  Siguiendo la idea del hint 2, recorriendo de forma decreciente en una de las características podemos mantener un Segment Tree donde el índice indica el orden en la 2a característica y los valores corresponden a la 3a característica. De esta forma con un query de máximo al segmento (i, end) donde i corresponda a uno más que el valor de la persona que se revisa actualmente, si el mayor valor es mayor que el valor de la 3a característica actualmente entonces debe haber una persona con mayores valores en cada característica.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Ball.cpp">Código de ejemplo</a>
</details>

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

###  - Xenia and Bit Operations
<details> 
  <summary>Hint</summary>
  Pinesen en cómo construir un nodo para poder resolver el problema con un Segment Tree
</details>
<details> 
  <summary>Solución + código</summary>
  Si en cada nodo guardamos el valor y la profundidad inversa (empezando desde 0 en las hojas), podemos realizar distintas operaciones en la unión de dos nodos dependiendo de la profundidad en la que se produzca la unión, es decir, si la profundidad es par unimos con or y si es impar unimos con xor. Ambas operaciones son compatibles con un Segment Tree y la complejidad final es O(m log(2^n))
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/XeniaAndBitOperations.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```
