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

### H - Sum

<details> 
  <summary>Hint</summary>
  Fijense que al aumentar la base a un número es imposible que sus dígitos aumenten, por lo tanto la mayor cantidad de dígitos se alcanza con la menor base posible
</details>
<details> 
  <summary>Solución + código</summary>
  Para solucionar el problema, según lo descubierto en el hint procedemos a encontrar en primer lugar la menor base posible, para esto basta recorrer los dígitos del input y guardar el mayor + 1. Posteriormente procedemos a sumar en esa base y guardar el largo del resultado, no es necesario obtener el resultado pues sólo nos importa su largo. Para sumar con respecto a una base B basta ir dígito por dígito y ver su suma, dividir por B y pasar el resultado a los siguientes dígitos (tal y como se enseña a sumar en el colegio). por ejemplo 18 + 17 en base 9, sumamos 8 + 7 = 15, dividimos por la base y nos queda 1, luego 1 + 1 = 2 luego sumamos lo que nos quedo de antes y obtenemos 3, al dividir por 9 no queda nada y terminamos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Sum.py">Código de ejemplo (Python)</a>, <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Sum.cpp">Código de ejemplo (C++)</a>
</details>

### I - Making Sequences is Fun

<details> 
  <summary>Hint</summary>   
  Una forma simple es ir acumulando la cantidad de números con cantidad de digitos d para cada d desde la cantidad de dígitos de m, como esto sube exponencialmente no es necesario muchas iteraciones.
</details>
<details> 
  <summary>Solución + código</summary>
  Como mencionamos en el hint, empezamos a acumular costo y cantidad de números para todos los números con cantidad de dígitos fija empezando desde la cantidad de dígitos de m, la cantidad de números con d dígitos es (10 ^ d - 10 ^ (d - 1)). En el momento en el que agregar todos estos números pase el máximo costo que podemos pagar, en vez de agregar todos estos números, sólo agregamos los que alcanzamos a pagar tomando el cuenta el costo acumulado que llevamos y el costo máximo total.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MakingSequencesIsFun.py">Código de ejemplo (Python)</a>, <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MakingSequencesIsFun.cpp">Código de ejemplo (C++)</a>
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
