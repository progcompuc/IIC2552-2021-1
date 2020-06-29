---
title: contest 12 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 12](../contests#contest-12) > ```{{page.title}}```

### A - Find a Number
<details> 
  <summary>Hint 1</summary>
  Notemos que podemos recorrer los números de mayor a menor con una especie de bfs, donde a partir de un número x agregamos a la cola todos aquellos números de la forma 10 x + i, con i dígito. Esto es útil pues si llegamos a descartar un número y no proseguir su bfs nos ahorramos pasar por todos los números que representan sucesores del número eliminado, reduciendo considerablemente el espacio de búsqueda.
</details>
<details> 
  <summary>Hint 2</summary>
  Notemos además que para cada número podemos obtener su resto resto respecto a d y la suma de sus dígitos, sin embargo como sólo nos interesan números con suma de dígitos de a lo más s, pues un número con suma mayor no puede generar el número que buscamos, entonces hay una cantidad finita de configuraciones (resto, suma) en los números que buscaremos, de hecho podemos concluir que dada una configuración (resto, suma), el óptimo de números a agregar será el mismo para todos los números con la misma configuración. Considerando lo anterior, no vale la pena volver a revisar configuraciones que ya han sido exploradas antes en el bfs.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución juntando todo lo anterior consiste en realizar un bfs en el árbol implícito descrito en el hint1, registrando como nodos las configuraciones finitas de (resto, suma). Además necesitamos llevar cuenta de qué configuraciones ya han sido visitadas. La primera vez que lleguemos a la configuración (0, s), es decir resto 0 (o divisible por d) y suma s, habremos tomado el camino óptimo, para reconstruir el camino basta haber registrado el parent de cada configuración generada, es decir qué configuración la agregó a la queue del bfs. Si nunca pasamos por la configuración (0, s), sabremos que no hay solución.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/FindANumber.cpp">Código de ejemplo</a>
</details>

### B - Yet Another Multiple Problem
<details> 
  <summary>Hint</summary>
  Revisen los hints del problema A, en este problema podemos usar una idea parecida pero adaptada a lo que piden.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución consiste en realizar el mismo bfs del problema A pero sólo considerando restos y los dígitos que estén permitidos, la primera vez que lleguemos a la configuración (0) habremos tomado el camino óptimo. De lo contrario no habrá solución.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/YetAnotherMultipleProblem.cpp">Código de ejemplo</a>
</details>

### C - Last digit
<details> 
  <summary>Hint</summary>
  Sacar factores primos del numerador y del denominador de la combinatoria puede servir.
</details>
<details> 
  <summary>Solución + código</summary>
  La combi que da la cantidad de permutaciones sin repetición es N!/(C[0]! * ... * C[25]!), donde C[i] es la cantidad de veces que está el caracter i. Precomputamos los primos hasta 10^6 con criba de eratóstenes y luego sacamos la factorización prima del numerador y de los factores del denominador linealmente con factorización prima de factoriales. Cancelamos exponentes, y luego matamos los 0's a la derecha matando los pares de 2 y 5 (min{ e[2], e[5] }). Luego el último dígito lo sacamos calculando el valor de la factorización módulo 10 usando binary exponentiation.
  <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/LiveArchive/4008_LastDigit.cpp">Código de ejemplo</a>
</details>

### D - Beautiful Numbers
<details> 
  <summary>Hint</summary>
  Lo más complicado del problema es calcular número de permutaciones sin repetición módulo 10^9+7.
</details>
<details> 
  <summary>Solución + código</summary>
  Iterar sobre k = 0, ..., N donde a es usado k veces y b usado (N-k) veces. Si (a*k + b*(N-k)) es good, entonces las N!/(k!x(N-k)!) permutaciones sin repeticiones son excelentes. Para calcular esa combi módulo 10^9+7, podemos calcularla como el producto del numerador con el inverso modular del denominador, que se puede obtener con euclides extendido. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/300C_BeautifulNumbers.cpp">Código de ejemplo</a>
</details>

### E - Forest for the Trees
<details> 
  <summary>Hint</summary>
  Para que exista un lattice point entre (0, 0) y (xb, yb) se necesita un punto cuya pendiente desde (0, 0) sea la misma que (xb, yb). Es decir, necesitamos que la fracción yb / xb, no sea irreducible. En caso de no ser una fracción irreducile, podemo reducirla al máximo dividiendo tanto el numerador como el denominador por el gcd(xb, yb) y definir x' = xb / g, y' = yb / g. De esta forma todos los lattice entre (0, 0) y (xb, yb) serán multiplos de (x', y').
</details>
<details> 
  <summary>Solución + código</summary>
  Para obtener el árbol más cercano a (0, 0) en caso de existir sólo hay 2 opciones, o es precisamente (x', y') descrito en el hint, o este punto estaa dentro del rectángulo talado. En el segundo caso necesitamos encontrar el primer múltiplo de (x', y') que esté fuera del rectángulo talado, esto se puede hacer de 2 formas, realizando búsqueda binaria sobre el factor o con una fórmula cerrada. La fórmula cerrada sale de obtener el factor como f = min(x2 / x', y2 / y') + 1, esto pues el el mínimo múltiplo de x' o y' que supera al rectángulo talado.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/ForestForTheTrees.cpp">Código de ejemplo</a>
</details>

### F - Almost Prime
<details> 
  <summary>Hint</summary>
  Dado un primo, todos sus múltiplos son divisibles por ese primo.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos modificar la criba de eratóstenes para ir marcando la cantidad de primos que dividen a cada número. Luego contamos cuántos números son divisibles por exactamente dos primos. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/26A_AlmostPrime.cpp">Código de ejemplo</a>
</details>

### G - Even Distribution
<details> 
  <summary>Hint 1</summary>
  Dado un camino arbitrario, la cantidad de niños correspondiente es el GCD de los dulces de cada nodo en el camino.
</details>
<details> 
  <summary>Hint 2</summary>
  Pensar en una forma de simular todos los posibles caminos pero podando caminos redundantes (que no van a aportar información nueva).
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos un BFS sobre un grafo de estados, donde los estados son pares (nodo, gcd). La cola del BFS la inicializamos con todos los pares (nodo, candies[nodo]). La idea es correr el BFS hasta explorar todos los estados alcanzables. Notar que si un estado ya visitado es re-visitado, no tiene sentido explorarlo porque todos los caminos que se puedan generar a partir de él tendrán el mismo gcd acumulado que los de la primera vez que fue visitado. La respuesta final va a ser la cantidad de distintos gcd's que hayamos visto (podemos meterlos en un set y retornar el tamaño del set). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/LiveArchive/6825_EvenDistribution.cpp">Código de ejemplo</a>
</details>

### H - Tile Painting
<details> 
  <summary>Hint</summary>
  Analizar la relación entre los divisores primos de n y los grupos de celdas que se pintan del mismo color.
</details>
<details> 
  <summary>Solución + código</summary>
  La respuesta es p si n sólo contiene un solo divisor primo p (o sea, n = p^e), o 1 si es que n contiene 2 o más factores primos. La razón es que cuando hay 2 o más factores primos, para cada par de factores primos siempre es posible encontrar una celda donde los grupos "se fusionan". Es decir, existe un índice i tal que i = r1 (mod p1) y i = r2 (mod p2), esto viene del teorema chino del resto (CRT). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1243C_TilePainting.cpp">Código de ejemplo</a>
</details>

### I - Candy's Candy
<details>
  <summary>Hint 1</summary>
  Si la suma de todos los candies es totC, el tamaño de un pack debe ser divisor de totC
</details>
<details> 
  <summary>Hint 2</summary>
  Si armamos packs de tamaño d, entonces:
  <ul>
    <li>d debe ser divisor de totC</li>
    <li>en total habrán k = totC/d packs</li>
    <li>como deben haber al menos F flavored packs y 1 variety pack, k debe ser >= F+1</li>
    <li>como debe haber un variety pack, entonces d debe ser múltiplo de F</li>
    <li>llamemos minC = min { C[i] for i = 1 ... F }, como cada flavor forma parte de un flavored pack y un variety pack, entonces minC >= d + d/F</li>
  </ul>
</details>
<details> 
  <summary>Hint 3</summary>
  Si tenemos una combinación (d, k) válida según el hint 2 (con d = tamaño del pack, k = número de packs), de base ya tenemos los F flavored packs y 1 variety pack obligatorios, por lo tanto por cada flavor nos sobra C[i] - (d + d/F) candies (para i = 1 .. F). Si vemos estos candies que nos sobran como F columnas de un histograma, podemos armar variety packs a lo sumo hasta la altura de la columna más chica. De ahí en adelante estamos obligados a usar flavored packs.
</details>
<details> 
  <summary>Hint 4</summary>
  Pensemos en una columna C[i] - (d + d/F) de nuestro histograma. Esta columna la tenemos que empaquetar con flavored packs (de tamaño d) o con variety packs (que van a restar d/F candies de esta columna). Esto significa que si calculamos el resto R[i] = (C[i]  - (d+d/F)) % d, este resto R[i] no puede ser empaquetado con flavored packs, la única opción es empaquetarlo con variety packs y por tanto R[i] debe ser múltiplo de (d/F). Además, si fijamos una cantidad X de variety packs, tenemos que asegurarnos de que el resto sea empaquetable con flavored packs (es decir, siempre nos tiene que sobrar múltiplos de d).
</details>
<details> 
  <summary>Hint 5</summary>
  Volviendo a nuestra definición R[i] = (C[i]  - (d+d/F)) % d del hint 4, este sobrante debe ser empaquetado con variety packs obligadamente, pero notar que un variety pack saca dulces de <strong>todos los flavors a la vez</strong>. Por lo tanto, concluimos que se debe cumplir que R[i] == R[j] para todo i, j (si no se cumple, no podemos empaquetar válidamente).
</details>
<details>
  <summary>Solución + código</summary>
  Calculamos totC = sum { C[i] for i = 1 ... F }, encontramos todos los divisores d válidos de totC según el hint 2. Luego por cada divisor contamos cuántos empaquetamientos distintos podemos hacer. Tenemos 2 casos: 1) Si con el empaquetamiento obligatorio quedó todo empaquetado (i.e. minC == maxC == d + (d/F)), entonces sumamos 1 al contador. 2) De lo contrario sobraron dulces en algunas columnas. Encontramos R[1] según el hint 4 y verificamos que R[i] == R[1] para i = 2 .. F, además calculamos Q[i] = (C[i] - (d+d/F)) / d (es decir, cuántos bloques de tamaño d nos caben en la columna i-ésima, usando división entera). Con eso podemos definir minQ = min { Q[i] para i = 1 .. F }. Entonces, volviendo a la visualización como histograma, estamos obligados a hacer variety packs hasta la altura R[1], y de ahí en adelante podemos hacer variety packs hasta la altura R[1] + d * 1, R[1] + d * 2, ..., R[1] + d * minQ (y en cada caso el resto lo empaquetamos con flavored packs). Por lo tanto sumamos minQ + 1 al contador. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/UVA/12358_Candy'sCandy.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 12](../contests#contest-12) > ```{{page.title}}```
