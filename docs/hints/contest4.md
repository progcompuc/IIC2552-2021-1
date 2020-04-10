---
title: contest 4 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```

### Weakness and Poorness
</details>
<details> 
  <summary>Hint</summary>
  Nos piden calcular el x que minimice el máximo de los valores absolutos de sumas por intervalos en el arreglo, esto se reduce a calcular el máximo entre las sumas positivas y las sumas negativas. Para calcular por ejemplo las sumas positivas basta recorrer un arreglo linealmente y para cada i almacenar la mayor suma positiva continua que termina en i, el máximo de las sumas positivas por intervalo corresponderá al mayor numero almacenado.
  </details>
<details>
  <summary>Solución + código</summary>
  Nos podemos fijar que para un x muy pequeño o muy grande el valor buscado aumenta, por lo que debemos buscar un punto intermedio, esto lo podemos hacer con búsqueda ternaria. Intentamos con valores de x entre -10000 y 10000 por los lámites del problema y para comparar los valores intermedios e la búsqueda calculamos weakness para ese valor en particular usando el hint. Para adaptar el hint a sumas negativas simplemente se puede usar el inverso de los valores del arreglo luego de restar x.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/WeaknessAndPoorness.cpp">Código de ejemplo</a>
</details>


<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```
