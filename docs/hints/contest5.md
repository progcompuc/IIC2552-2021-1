---
title: contest 5 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```

### A - A problem of Backtracking
<details> 
  <summary>Hint</summary>
  Gracias a los límites este problema se puede resolver de dos formas:
  1) fuerza bruta pura: iterar sobre todas las permutaciones lexicográficamente (muy fácil)
  2) backtracking: iterar sobre todas las permutaciones con una función recursiva y agregando podas (un poquito más difícil pero vale la pena)
</details>
<details> 
  <summary>Solución + código</summary>
  Si usamos la opción uno del hint, la solución es facilísima. En C++ existe la función next_permutation() que nos permite iterar sobre las permutaciones en orden lexicográfico. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/BTCK_A-problem-of-Backtracking_v1.cpp">Código de ejemplo 1</a>.
  La otra opción es hacerlo con backtracking. En este caso podemos construir la permutación de izquierda a derecha, en cada posición iterando sobre los dígitos de 0 a 9 (de menor a mayor, para iterar en orden lexicográfico). Podemos agregar podas. Dos podas que se me ocurrieron a mí: 1) descartar dígitos que ya se pusieron antes y 2) descartar dígitos que al ponerlos hacen que nuestra suma hasta el momento supere la cota K. Para la primera podemos agregar un argumento 'mask' a la función del backtracking cuyos bits nos indican los dígitos ya puestos, y para la suma hasta el momento podemos agregar un argumento 'accsum' con la suma acumulada. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/BTCK_A-problem-of-Backtracking_v2.cpp">Código de ejemplo 2</a>.
</details>

### B - ALL IZZ WELL
<details> 
  <summary>Hint</summary>
  Si fijamos un punto de partida en la matriz, entonces podemos hacer backtracking para explorar todo el universo de posibles caminos válidos que forman el string "ALLIZZWELL" que comienzan en esa posición. Para ello, notar que en cada paso tenemos que ir decidiendo cuál va a ser nuestra siguiente celda.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos un doble for iterando sobre todas las celdas. Por cada celda, asumimos que dicha celda es nuestro punto de partida y lanzamos un backtracking para encontrar un camino que forme el string "ALLIZZWELL". En cada llamada de la función backtracking verificamos si la celda en que estamos parados tiene el caracter que corresponde al índice actual en el que vamos en "ALLIZZWELL". Luego intentamos completar el resto del path recursivamente llamando la función de backtracking sobre alguna de las 8 celdas adyacentes (siempre y cuando la celda adyacente no haya sido visitada ya, eso se puede chequear con una matriz booleana auxiliar). Si en algún momento un backtracking retorna true, se puede, si todos los backtrackings retornaron false, no se puede.  <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/ALLIZWEL.cpp">Código de ejemplo</a>.
</details>

### B - ALL IZZ WELL
<details> 
  <summary>Hint</summary>
  Si fijamos un punto de partida en la matriz, entonces podemos hacer backtracking para explorar todo el universo de posibles caminos válidos que forman el string "ALLIZZWELL" que comienzan en esa posición. Para ello, notar que en cada paso tenemos que ir decidiendo cuál va a ser nuestra siguiente celda.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos un doble for iterando sobre todas las celdas. Por cada celda, asumimos que dicha celda es nuestro punto de partida y lanzamos un backtracking para encontrar un camino que forme el string "ALLIZZWELL". En cada llamada de la función backtracking verificamos si la celda en que estamos parados tiene el caracter que corresponde al índice actual en el que vamos en "ALLIZZWELL". Luego intentamos completar el resto del path recursivamente llamando la función de backtracking sobre alguna de las 8 celdas adyacentes (siempre y cuando la celda adyacente no haya sido visitada ya, eso se puede chequear con una matriz booleana auxiliar). Si en algún momento un backtracking retorna true, se puede, si todos los backtrackings retornaron false, no se puede.  <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/ALLIZWEL.cpp">Código de ejemplo</a>.
</details>

### C - 8 Queens Chess Problem
<details> 
  <summary>Hint</summary>
  Dos reinas no pueden compartir columna, así que podemos primero simplificar el problema a tener una reina por columna. Entonces ahora el problema se nos reduce a iterar sobre las columnas y en cada columan decidir en qué fila poner la reina de esa columna (excepto para la columna de la reina fija, donde estamos obligados a hacerle caso al input). Entonces podemos hacer backtracking para explorar este árbol de decisiones y encontrar todas las soluciones, aprovechando las líneas de ataque de las reinas para hacer muchas podas.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos un backtracking que recibe como argumento la columna actual (inicialmente c = 0), e iteramos sobre las celdas de la columna verticalmente. Cada vez que haya una celda vacía que no esté siendo atacada por una reina ya puesta, intentamos la opción de poner la reina de esta columna ahí. Al hacer esto, en una matriz auxiliar le sumamos 1 a cada celda que es atacada por esta reina. Cuando hagamos backtrack, tenemos que restarle 1 a cada celda atacada por la reina (para hacer el "undo" del +1 que hicimos antes). Una celda no es atacada si su contador es igual al 0. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/UVA/750_8-Queens-Chess-Problem.cpp">Código de ejemplo</a>.
</details>


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

### H - Tight-Fit Sudoku
<details> 
  <summary>Hint</summary>
  Este es un backtracking clásico donde debemos ir probando los números en cada celda hasta generar una configuración adecuada según el enunciado. Una forma de acelerar el código es no almacenar los números ocupados por fila/columna/subgrilla en arreglos o set y ocupar bits y bitwise operations.
</details>
<details> 
  <summary>Solución + código</summary>
  La solucion consiste en tener bits asociados a cada columna/fila/subgrilla que almacenan los números que ya hemos ocupado. Luego usamos backtracking para provar distintos valores en las celdas del sudoku. Mientras se tenga cuidado de no olvidar alguna de las reglas, el código es bastante directo.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/Tight-FitSudoku.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```
