---
title: contest 11 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 11](../contests#contest-11) > ```{{page.title}}```

### A - Dazzling Stars
<details> 
  <summary>Hint 1</summary>
  Se puede reinterpretar como ver si existe un vector (o dirección con sentido) donde al proyectar las estrellas nunca aparezca una estrella de mayor brillo antes que una de menor brillo. Siempre existirá esta dirección si los vectores que van de estrellas de menor brillo a mayor brillo no son incompatibles.
</details>
<details> 
  <summary>Hint 2</summary>   
  Si ordenamos los vectores que van de menor a mayor brillo por ángulo, serán compatibles si existe un rango de 180 que los contiene a todos.
</details>
<details> 
  <summary>Solución + código</summary>
  Basta hacer un sweepline radial con eventos de inicio y final de rango para cada vector. Si tenemos un vector v, agregaremos sus rotaciones en +- 90 grados al sweepline como inicio y fin de rango. Si al recorrer los eventos en orden en algún momento todos los rangos están activos la respuesta será Y.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Matcomgrader/DazzlingStars.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 11](../contests#contest-11) > ```{{page.title}}```
