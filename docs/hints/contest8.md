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

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```
