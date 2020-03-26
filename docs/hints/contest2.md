---
title: contest 2 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```

### E - Counting Stars

<details> 
  <summary>Hint</summary>
  Si visitamos cada posicion del arreglo una por una para contar, deben buscar una forma de una vez empezado a ver una estrella marcar todas las celdas que la componen antes de seguir, para no contar dos veces la misma estrella
</details>
<details> 
  <summary>Solución + código</summary>
  Tal como se dijo en el código empezamos a revisar celda por celda y si es que encontramos el inicio de una estrella, marcamos como vistas todas las posiciones que la componen antes de seguir. Para poder hacer esto podemos hacer uso de una función recursiva que dado un punto empiece a revisar recursivamente sus vecinos parte de la estrella, marcamos cada celda al visitarla para no repetir. Este acercamiento a la solución se conoce como DFS (Depth First Search).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/CountingStars.cpp">Código de ejemplo (C++)</a>
</details>

### J - Hyperset

<details> 
  <summary>Hint 1</summary>
  Si fijamos dos cartas, notar que hay una única posible tercera carta que puede completar el trío de forma válida.
</details>
<details>
  <summary>Solución + código</summary>
  Iteramos sobre todos los posibles pares (for i in range(n): for j in range(i+1,n)) de cartas, y entonces calculamos la única tercera carta válida (para cada caracter, si son iguales, entonces usamos ese caracter, y si son distintos, buscamos el tercer caracter que no se ha usado). Luego chequeamos si esa carta existe (usamos un set/unordered_set para chequear esto rápido). Si la carta existe entonces sumamos 1 a un contador. Recordar dividir el contador por 3! para no incluir las permutaciones en el conteo. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1287B_Hyperset.py">Código de ejemplo (Python)</a>, <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1287B_Hyperset.cpp">Código de ejemplo (C++)</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```
