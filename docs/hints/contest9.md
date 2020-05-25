---
title: contest 9 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 9](../contests#contest-9) > ```{{page.title}}```

### A - Merge Sort

<details> 
  <summary>Hint</summary>
  Necesitamos un arreglo que al llamar mergesort sobre él, se hagan un total de K llamadas. Pensar en una forma de simular la ejecución de mergesort distribuyendo hacia abajo las K llamadas totales que hay que hacer, y en vez de ordenar vamos poniendo valores desordenados (cosa de que al llamar el mergesort original se ejecuten esas mismas K llamadas que simulamos).
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos la misma recursión divide and conquer de mergesort(l, r, k), donde le agregamos un argumento extra k que nos dice cuantas llamadas tenemos que hacer. Si k == 1, entonces esta llamada en particular debe ser una llamada final (no más recursión hacia abajo), así que el subarreglo correspondiente debe estar ordenado (llenamos con valores crecientes). Si k > 1, entonces hay que decidir cómo repartir (k-1) llamadas entre las dos llamadas hijas. Pueden haber varias opciones. Una opción posible es tirar la mayor cantidad de llamadas a la izquierda y lo que sobre a la derecha. Como sea que distribuyamos, nos van a quedar los dos subarreglos hijos con valores asignados. Para garantizar que la unión de los dos subarreglos quede desordenada, le podemos sumar un offset a los valores del subarreglo hijo izquierdo para garantizar que todos esos valores sean mayores estrictos a los valores del subarreglo derecho (con eso queda sí o sí desordenado). Los casos bordes en que se retorna -1 son cuando el k supera el máximo de llamadas posibles o bien cuando k es par. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/873D_MergeSort.cpp">Código de ejemplo</a>
</details>

### B - Practice

<details> 
  <summary>Hint</summary>
  Notar que si tenemos un grupo de n personas y queremos repartirlos en dos grupos que maximicen la cantidad de pares, lo óptimo es repartidos en dos grupos de n/2 (si n es par) o lo más cercano a eso (floor(n/2) y n-floor(n/2)).
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos una función search(l, r, i) que reparte los jugadores l, l+1, l+2, ..., r-1 entre dos equipos desde la sesión de práctica i en adelante (la profundida de la recursión corresponde al índice de la sesión de práctica). En cada llamada, calculamos m = (l+r)/2, entonces los jugadores desde l hasta m-1 se van al equipo 1 en la sesión de práctica i. Luego se llama a search(l, m, i+1) y search(m, r, i+1). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/234G_Practice.cpp">Código de ejemplo</a>
</details>

### C - Painting Fence

<details> 
  <summary>Hint</summary>
  Si tienes una cerca de ancho N, piensa en las formas de pintar el rectángulo de ancho N y altura 1 ubicado en el piso (la base de la cerca). Lo puedes pintar con un brochazo horizontal (costo 1), pero luego te faltaría pintar todo lo de arriba (la misma cerca pero restándole 1 a todas las alturas), o bien puedes pintar el rectángulo con N brochazos verticales (costo N, pero con eso pintas la cerca completa). Mezclar brochazos horizontales y verticales para el rectángulo basal no tiene sentido ya que en ese caso aprovechas de pintar el rectángulo entero con un puro brochazo horizontal y te ahorras todos los brochazos verticales. Ahora, no es dificil generalizar el razonamiento a todo el rectángulo basal de altura hmin, donde hmin es la altura mínima de la cerca.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos una función recursiva para pintar paint(l, r, h) que calcula el costo óptmo de pintar la subcerca entre los índices l y r y considerando todo lo que está arriba de la altura h. El problema original se resuelve con paint(0, N, 0). Entonces en cada llamada tenemos dos opciones, pintar el rectángulo que va desde h hasta hmin(l, r) con brochazos horizontales (con lo cual nos quedarían subsubcercas aisladas por pintar recursivamente) o bien pintamos todo vertical de un viaje. Retornamos el mínimo entre ambas opciones. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/448C_PaintingFence_v2.cpp">Código de ejemplo</a>
</details>

### D - Code For 1

<details> 
  <summary>Hint</summary>
  Pensar que tenemos un árbol binario donde la raíz es n, las dos nodos hijos inmediatos son floor(n/2) y floor(n/2), luego en el tercer nivel hay 4 nodos floor(floor(n/2)/2), etc. Cada nodo está a cargo de un subrango de índices del arreglo final. Por ej. la raíz n genera la lista completa, así que su rango es todo el arreglo, o sea [0, size(n)-1], donde size(n) es el tamaño del arreglo final generado por n. Pensar en una forma de responder la consulta [l, r] como si estuvieramos navegando este árbol binario implícito, y descartamos nodos que no aportan a la consulta (por ej. si un nodo está a cargo del rango [i, j] y dicho rango tiene intersección vacía con [l, r], podemos descartar ese nodo y todo su subárbol para abajo).
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos un divide and conquer navegando recursivamente sobre el árbol binario implícito explicado en el hint, donde en cada llamada recursiva vamos pasando hacia abajo el rango de índices correspondiente a cada nodo, y descartamos nodos que no aportan a la query [l,r]. Si un nodo está completamente contenido en la query, podemos retornar altiro la cantidad de 1s que hay en ese nodo (no es necesario seguir haciendo recursión). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/768B_CodeFor1.cpp">Código de ejemplo</a>
</details>

### E - Guardians of the Lunatics
<details> 
  <summary>Hint 1</summary>
  Es relativamente simple pensar en un dp que soluciona este problema pero este no pasará en el límite de tiempo del problema. Un posible dp como el mencionado arriba es resolver cómo asignar x guardias a los primeros y lunáticos, esto será el mínimo de todas las posibilidades de asignar 1 de los guardias (su costo) y del mismo dp en (x - 1, y - c) donde c es la cantidad asignada al último guardia (el que estamos decidiendo ahora). Este dp sin embargo tiene complejidad O(G*L^2) por lo que necesitamos optimizarlo para pasar en tiempo. Piensen en una optimización del estilo divide and conquer.
</details>
<details> 
  <summary>Hint 2</summary>  
  Si fijamos x, y analizamos el índice en que se logra el mínimo (al iterar para asignar el último de los x guardias) en el dp mencionado para los estados (x, i) con i de 1 a L, podemos notar que este índice es creciente c/r a i. Es decir opt[i] <= opt[j] si i < j.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando lo anteriormente mencionado podemos haer una optimización del estilo divide and conquer a nuestro dp, donde no es necesario iterar en todas las posibilidades de 0 a i para asignar el último guardia, sino que podemos usar cotas en izquierda y derecha para acotar el espacio de búsqueda. Para aprender más al respecto pueden ver el siguiente  <a href="https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html">link</a>. La complejidad final es de O(G*L*log(L)) que pasa en tiempo.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/HackerRank/GuardiansOfTheLunatics.cpp">Código de ejemplo</a>
</details>

### F - Tricky Function
<details> 
  <summary>Hint</summary>
  Notemos que si precalculamos las sumas parciales en un arreglo s, donde s[i] representa la suma de a[1] hasta a[i] entonces podemos reescribir f(i, j) = (j - i)^2 + (s[j] - s[i])^2. Notemos que minimizar esto es lo mismo que encontrar la distancia mínima entre puntos del estilo (i, s[i]) en el plano 2D. Luego el problema se reduce a encontrar el par de puntos más cercanos en un set.
</details>
<details> 
  <summary>Solución + código</summary>
  Una forma naive para encontrar el par de puntos más cercanos es checkear cada par, lo que es O(n^2) que no pasa en tiempo.
  Hay un approach clásico divide and conquer para solucionar el problema de par de puntos más cercanos en O(n*log(n)). Para aprender más al respecto pueden revisar los siguientes links:
  
  <a href="https://www.geeksforgeeks.org/closest-pair-of-points-using-divide-and-conquer-algorithm/">O(n*log(n)^2)</a>.
  
  <a href="https://www.geeksforgeeks.org/closest-pair-of-points-onlogn-implementation/?ref=rp">O(n*log(n))</a>.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TrickyFunction.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 9](../contests#contest-9) > ```{{page.title}}```
