---
title: contest 8 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```

### A - Filling Shapes
<details> 
  <summary>Solución + código</summary>
  Si la cantidad de columnas es impar, es imposible rellenar, en otro caso siempre hay dos formas por cada dos columnas, luego la respuesta es 2^(N / 2).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/FillingShapes.cpp">Código de ejemplo</a>
</details>

### B - Santa Claus and Candies
<details> 
  <summary>Hint</summary>   
  La forma óptima de entregar dulces siempre será 1 al primero, 2 al segundo, ... y al último que alcances todo lo que te quede.
</details>
<details> 
  <summary>Solución + código</summary>
  La suma de 1 + 2 + ... + N = N * (N + 1) / 2, luego basta ver en qué momento esto se pasa de la cantidad de dulces que tienes y entregar el N justo antes de que se pase. Usar la estrategia del Hint para repartir.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/SantaClausAndCandies.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```
