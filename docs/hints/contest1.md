---
title: contest 1 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 1](../contests#contest-1) > ```{{page.title}}```

### B - Roadwork
<details> 
  <summary>Hint 1</summary>
  Para facilitar el análisis, en vez de pensar para cada persona con qué obstáculo choca, lo podemos ver como para cada obstáculo, qué personas detiene.
  Podemos ver que el obtáculo en X entre S y T detiene a la persona que parte en D si S - X <= D < T - X.
</details>
<details> 
  <summary>Hint 2</summary>
  Si analizamos los obstáculos y las personas en orden temporal (obstáculos tomando tiempo entre los que si una persona sale choca con el) y llevamos cuenta de los intervalos activos, podemos responder la distancia que caminará (en caso de parar) si mantenemos la posición de los obstáculos en una estructura ordenada.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos generar un vector de eventos temporales el cual recorreremos en orden, los eventos pueden ser, empieza el efecto de un obstáculo (S - X como en Hint 1), termina el efecto de un obstáculo y sale una persona. Al recorrer el vector, basta mantener un multiset ordenado con la posición de los obstáculos que estén activos para poder responder la distancia caminada para cada persona en O(1) cuando salga el evento correspondiente y con updates en O(log N) al empezar o terminar alguno.
  La complejidad total de esta solución es O((N + Q) log(N + Q))
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/AtCoder/Roadwork.cpp">Solución ejemplo</a>
</details>

### C - Two Teams
<details> 
  <summary>Hint 1</summary>
  Podemos ordenar los estudiantes del con mayor habilidad al con menos habilidad podemos agregarlos a un MaxHeap, que agrega elementos en O(log N), consulta por el mayor en O(1) y quita el mayor en O(log N).
</details>
<details> 
  <summary>Hint 2</summary>
  Podemos visitar uno por uno los estudiantes y marcar el equipo correspondiente a los alumnos k a la derecha y a la izquierda no marcados, el problema es que si visitamos muchas veces estudiantes no marcados el algoritmo no cae en el límite de tiempo. Debemos encontrar una forma de no visitar más que una vez cada estudiante. Una estructura perfecta para esto es una lista ligada tal que podamos eliminar segmentos de un arreglo en O(1).
</details>
<details> 
  <summary>Solución + código</summary>
  Recorremos en orden los estudiantes, para cada uno, si no ha sido marcado marcamos k a la derecha y a la izquierda de la lista y eliminamos el segmento.
  Podemos simular la lista ligada usando vectores R, L, tal que R[i] indica qué indice está actualmente a la derecha de i y L[i] a la izquierda de i. al eliminar un segmento sólo debemos unir el de la izquierda del primer eliminado con el de la derecha del último, así en consultas siguientes no se pasará por lo eliminado.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TwoTeams.cpp">Código de ejemplo</a>
</details>

### F - Weird Function
<details> 
  <summary>Hint</summary>
  La clave del problema es ordenar los datos de una forma que permita acceder eficientemente a la mediana de estos ordenados.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos mantener un MaxHeap con la mitad inferior de los datos y un MinHeap con la mitad superior de los datos, tal que podemos acceder a la mediana como el tope del MaxHeap inferior en O(1). Cada vez que agregamos un dato lo agregamos al MaxHeap, si el mayor del MaxHeap es mayor que el menor del MinHeap hacemos un swap de estos datos, y si se desequilibran en tamaño pasamos el mayor del MaxHeap al MinHeap.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/WeirdFunction.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 1](../contests#contest-1) > ```{{page.title}}```
