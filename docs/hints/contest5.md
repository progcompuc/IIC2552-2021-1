---
title: contest 5 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```

### E - Map Colouring
<details> 
  <summary>Hint</summary>
  Podemos crear un backtracking que nos responda si es posible colorear el mapa con a lo más k colores, para esto solo basta decidir un color entre 1 y k para cada país de forma que no coincida con sus vecinos.
</details>
<details> 
  <summary>Solución + código</summary>
  Si usamos un backtracking que nos responda según lo especificado en el hint, basta probar con los números entre 1 a 4 como máxima cantidad de colores e imprimir el primero que funcione, si ninguno lo hace imprimimos "many".
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/MapColouring.cpp">Código de ejemplo</a>
</details>

### F - Limited Correspondence
<details> 
  <summary>Hint</summary> 
  Notar que por la cantidad de palabras tenemos el tiempo suficiente para probar cada par de palabras en cada posición del 1 al 11 (en el peor caso), de esta forma podemos detectar todas las posibles soluciones y guardar la "mejor" según enunciado.
</details>
<details> 
  <summary>Solución + código</summary>
  Una posible solución consiste en realizar un backtracking sobre el orden en el que vamos tomando los pares, cada vez que en la construcción de este orden tengamos que las dos palabras parciales son iguales, no seguimos agregando, pues ninguna solución óptima puede ser más larga. Cada vez que tengamos una solución la comparamos con la mejor hasta el momento y devolvemos la mejor al final. Tener cuidado en la implementación de ser eficiente en el manejo de los strings, comparaciones extras y mal manejo de los updates en los strings parciales puede llevar a TLE en el problema.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/LimitedCorrespondence.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```
