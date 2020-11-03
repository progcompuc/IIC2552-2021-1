---
title: contest 8 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```

### B - Queries for Number of Palindromes
<details> 
  <summary>Hint 1</summary>
  Dado el tamaño del string podemos preprocesar todos los substrings cuadráticamente para saber cuáles conforman palíndromos, esto puede ser chequeado con Rolling Hashing hacia ambos lados por ejemplo. Piensen en cómo usar este preprocesamiento para obtener la solución.
</details>
<details> 
  <summary>Hint 2</summary>
  Dados l y r, la cantidad de substrings en [l, r] es la cantidad en [l, r - 1] más la en [l + 1, r] menos la en [l + 1, r - 1] más 1 si el mismo substring [l, r] era un palíndromo.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando los hints anteriores se puede armar un algoritmo de programación dinámica que cuente los substrings que son palíndromos para cada l y r usando la recursión del hint 2.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/QueriesForNumberOfPalindromes.cpp">Código de ejemplo</a>
</details>

### C - Isomorphic Inversion
<details> 
  <summary>Hint</summary>
  Piensen en una forma greedy de seleccionar los segmentos.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos armar los segmentos de forma greedy chequenando con k de 1 creciente separando los primeros y últimos k cada vez que el sustring de los primeros k que quedan sea igual al de los últimos k. Para chequear esto se puede usar hashing preprocesado de todo el string. la respuesta será cuantas veces se pudo separar * 2 más uno si sobraron cosas al medio.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/IsomorphicInversion.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```
