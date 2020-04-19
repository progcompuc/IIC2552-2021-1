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

### C - 8 Queens Chess Problem
<details> 
  <summary>Hint</summary>
  Dos reinas no pueden compartir columna, así que podemos primero simplificar el problema a tener una reina por columna. Entonces ahora el problema se nos reduce a iterar sobre las columnas y en cada columna decidir en qué fila poner la reina de esa columna (excepto para la columna de la reina fija, donde estamos obligados a hacerle caso al input). Entonces podemos hacer backtracking para explorar este árbol de decisiones y encontrar todas las soluciones, aprovechando las líneas de ataque de las reinas para hacer muchas podas.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos un backtracking que recibe como argumento la columna actual (inicialmente c = 0), e iteramos sobre las celdas de la columna verticalmente. Cada vez que haya una celda vacía que no esté siendo atacada por una reina ya puesta, intentamos la opción de poner la reina de esta columna ahí. Al hacer esto, en una matriz auxiliar le sumamos 1 a cada celda que es atacada por esta reina. Cuando hagamos backtrack, tenemos que restarle 1 a cada celda atacada por la reina (para hacer el "undo" del +1 que hicimos antes). Una celda no es atacada si su contador es igual al 0. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/UVA/750_8-Queens-Chess-Problem.cpp">Código de ejemplo</a>.
</details>

### D - Sum it up
<details> 
  <summary>Hint</summary>
  Supogamos que tenemos los números usados y sus frecuencias (cuántas veces tenemos cada número duplicado). Entonces podemos explorar todo el universo de soluciones como un árbol de decisiones con backtracking, donde la secuencia de decisiones es: cuántas veces uso el primer número, cuántas veces uso el segundo número, ..., cuántas veces uso el último número.
</details>
<details> 
  <summary>Solución + código</summary>
  Encotramos todas las soluciones con backtracking, explorando el árbol de soluciones indicado en el hint. Para encontrar las soluciones de mayor a menor, ordenamos los números de mayor a menor y además por cada número iteramos de mayor a menor en la cantidad de veces que lo usamos (de frecuencia[número] a 0). Como poda podemos chequear que si poner un número una cantidad X de veces hace que nos pasemos de la suma, entonces descartamos ponerlo. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/LiveArchive/5319_SumItUp.cpp">Código de ejemplo</a>.
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

### G - Vitamins
<details> 
  <summary>Hint</summary>
  Para hacerlo con backtracking, podemos pensar que por cada jugo tenemos que tomar la decisión de comprarlo o no. Esto naturalmente nos da un árbol de decisiones. Explorar todas las ramas nos daría tiempo O(2^N), así que la idea es usar muy buenas podas.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos backtracking según el hint. Como podas, podemos detectar cuando ya tenemos todas las vitaminas y cortar la búsqueda, también podemos sólo considerar la opción de comprar un jugo sólo si dicho jugo aporta vitaminas nuevas que no hemos visto antes, y también podemos tener una variable global con el costo más barato visto a la fecha, y sólo comprar un jugo si la solución parcial que estamos armando tiene un costo menor estricto al de la mejor solución a la fecha. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1042B_Vitamins.cpp">Código de ejemplo</a>
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

### I - Magical Mystery Knight's Tour
<details> 
  <summary>Hint 1</summary> 
  Para ver este problema como backtracking se puede plantear como un problema de decidir el camino del caballo posición por posición evitando repetir y coincidiendo con los pasos predeterminados por el input. La idea es probar todos los caminos que nos lleven al siguiente número determinado con las celdas disponibles. Ojo que es necesario usar buenas podas para pasar en el tiempo límite. 
</details>
<details>
  <summary>Hint 2</summary> 
  Podemos notar que al final del proceso todas las filas y columnas deben sumar 260. Una buena poda para este problema es evitar continuar con una exploración si no es posible llegar a 260 alguna de las filas o culumnas del tablero con los números restantes. Para esto basta tener guardadas las sumas de los números ya determinados en cada fila/columna y ver si el rango de posibles valores a los que puede llegar cada una con los números restantes contiene a 260. Si no lo hace podemos hacer "backtrack" sin riesgo a no encontrar la solución.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución consiste en realizar lo expresado en los hints. Para recorrer el tablero de forma óptima se pueden guardar los movimientos del cabayo en un arreglo y probar cada uno de ellos al realizar el backtracking. Guardamos sumas acumuladas por filas y columnas y realizamos las podas adecuadas. OJO: En este problema consideraremos que con pasar 51/52 tests cases se acepta la solución, esto porque el tiempo límite del judge es bastante ajustado.
  <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/kattis/MagicalMysterKnightsTour.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```
