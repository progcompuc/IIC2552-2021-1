---
title: contest 5 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```

### A - Map Colouring
<details> 
  <summary>Hint</summary>
  Podemos crear un backtracking que nos responda si es posible colorear el mapa con a lo más k colores, para esto solo basta decidir un color entre 1 y k para cada país de forma que no coincida con sus vecinos.
</details>
<details> 
  <summary>Solución + código</summary>
  Si usamos un backtracking que nos responda según lo especificado en el hint, basta probar con los números entre 1 a 4 como máxima cantidad de colores e imprimir el primero que funcione, si ninguno lo hace imprimimos "many".
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/MapColouring.cpp">Código de ejemplo</a>
</details>

### B - A problem of Backtracking
<details> 
  <summary>Hint</summary>
  Podemos armar un backtracking que vaya número por número viendo en que lugar se agrega a la suma en forma de función solve(indice, suma actual), para cada dígito, debemos ver si lo agragamos como unidad, decena, centena, etc...
</details>
<details> 
  <summary>Solución + código</summary>
  Usando el hint, si en algún momento luego de pasar por todos los índices se tiene una suma menor a K retornamos hacia atrás quedando guardado las posiciones donde funcionó.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/AProblemOfBacktracking.cpp">Código de ejemplo</a>
</details>

### C - ALL IZZ WELL
<details> 
  <summary>Hint</summary>
  Si fijamos un punto de partida en la matriz, entonces podemos hacer backtracking para explorar todo el universo de posibles caminos válidos que forman el string "ALLIZZWELL" que comienzan en esa posición. Para ello, notar que en cada paso tenemos que ir decidiendo cuál va a ser nuestra siguiente celda.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos un doble for iterando sobre todas las celdas. Por cada celda, asumimos que dicha celda es nuestro punto de partida y lanzamos un backtracking para encontrar un camino que forme el string "ALLIZZWELL". En cada llamada de la función backtracking verificamos si la celda en que estamos parados tiene el caracter que corresponde al índice actual en el que vamos en "ALLIZZWELL". Luego intentamos completar el resto del path recursivamente llamando la función de backtracking sobre alguna de las 8 celdas adyacentes (siempre y cuando la celda adyacente no haya sido visitada ya, eso se puede chequear con una matriz booleana auxiliar). Si en algún momento un backtracking retorna true, se puede, si todos los backtrackings retornaron false, no se puede. 
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/ALLIZZWELL.cpp">Código de ejemplo</a>.
</details>

### D - 8 Queens Chess Problem
<details> 
  <summary>Hint</summary>
  Podemos iterar en el backtracking sobre todas las celdas intentando poner una reina, una función solve(fila, columna, número de reinas hasta ahora) lograría esto, cada vez que ponemos una reina marcamos las celdas que ataca como ocupadas y continuamos revisando. (Tener cuidado de desmarcar luego de terminar de revisar un subarbol, para marcar basta sumar 1 a las celdas y desmarcar restar 1).
</details>
<details> 
  <summary>Solución + código</summary>
  Si en algún momento llegamos a poner 8 reinas guardamos las posiciones en un set de respuesta y continuamos el backtracking.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/UVA/8QueensChessProblem.cpp">Código de ejemplo</a>.
</details>

### E - Sum it up
<details> 
  <summary>Hint</summary>
  Podemos armar una función de backtracking solve(indice, suma actual) que itere sobre los números de mayor a menor viendo si los agrega a la suma o no.
</details>
<details> 
  <summary>Solución + código</summary>
  Ocuoando el hint, si en algún momento la suma es exactamente lo que queremos guardamos los números elegidos en un set de respuesta para devolver las posibilidades de mayor a menor lexicográficamente. Ojo con no seguir explorando una vez que la suma supera el objetivo.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Otros/SumItUp.cpp">Código de ejemplo</a>.
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
  Hacemos backtracking según el hint. Como podas, podemos detectar cuando ya tenemos todas las vitaminas y cortar la búsqueda, también podemos sólo considerar la opción de comprar un jugo sólo si dicho jugo aporta vitaminas nuevas que no hemos visto antes, y también podemos tener una variable global con el costo más barato visto a la fecha, y sólo comprar un jugo si la solución parcial que estamos armando tiene un costo menor estricto al de la mejor solución a la fecha.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Vitamins.cpp">Código de ejemplo</a>
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
  Podemos notar que al final del proceso todas las filas y columnas deben sumar 260. Una buena poda para este problema es evitar continuar con una exploración si no es posible llegar a exactamente 260 en alguna de las filas o columnas del tablero con los números restantes. Para esto basta tener guardadas las sumas de los números ya determinados en cada fila/columna y ver si el rango de posibles valores a los que puede llegar cada una con los números restantes contiene a 260. Si no lo hace podemos hacer "backtrack" sin riesgo a no encontrar la solución.
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
