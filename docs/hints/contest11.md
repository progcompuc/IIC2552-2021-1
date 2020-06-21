---
title: contest 11 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 11](../contests#contest-11) > ```{{page.title}}```

### A - Almost Shortest Path

<details>
  <summary>Hint 1</summary>
  Sea L(u,v) la distancia más corta desde u hasta v (si no existe un camino, L(u,v) = infinito). Una arista (u,v) es parte de algún camino más corto desde S a D si y sólo si L(S,u) + w_{u,v} + L(v,D) = L(S,D).
</details>
<details>
  <summary>Hint 2</summary>
  Notar que en el Hint 1 necesitamos ser capaces de calcular L(S,u) y L(u,D) para cualquier posible nodo u (recordar que S y D son fijos). Piensa en una forma de calcular eficientemente ambos para todos los nodos.
</details>
<details>
  <summary>Solución + código</summary>
  Para calcular L(S,u) para cada nodo u, corremos dijkstra desde S en el grafo G. Para calcular L(u,D), corremos dijkstra desde D sobre un grafo G' equivalente al grafo G con las aristas invertidas. Luego iteramos sobre todas las aristas (u,v) y aquellas que cumplan la propiedad del hint 1 las descartamos, y las demás las agregamos en nuevo grafo G''. Finalmente corremos un tercer dijkstra en G'' desde S y reportamos la distancia hasta D (o -1 si no se puede llegar). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/SAMER08A_AlmostShortestPath.cpp">Código de ejemplo</a>
</details>

### C - All Pairs Shortest Path

<details>
  <summary>Hint</summary>
  Por la materia vista, obviamente floyd warshall, pero cuidado con los casos bordes. Notar que el enunciado no menciona restricciones sobre sobre cómo puede ser el grafo. Eso quiere decir que en teoría podrían haber múltiples aristas entre dos nodos y también self-loops (de un nodo a sí mismo).
</details>
<details>
  <summary>Solución + código</summary>
  Básicamente floyd warshall con el extra para detectar ciclos negativos (ver materia en sección grafos) y teniendo cuidado con manejar los casos bordes mencionados. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/kattis/AllPairsShortestPath.cpp">Código de ejemplo</a>
</details>

### D - Wormholes

<details>
  <summary>Hint</summary>
  Bellman Ford
</details>
<details>
  <summary>Solución + código</summary>
  Bellman Ford básicamente, más el extra para pillar ciclos negativos (ver materia sección grafos). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/UVA/558_Wormholes.cpp">Código de ejemplo</a>
</details>

### E - Segments

<details>
  <summary>Hint 1</summary>
  Notar que las alturas dan lo mismo, sólo importan los intervalos en el eje X.
</details>
<details>
  <summary>Hint 2</summary>
  Si podemos lanzar rayos verticales tal que ningún intervalo es atravesado por más de R rayos, entonces también se puede lograr con R+1, R+2, etc. Simétricamente, si no es posible lograrlo con una cota de R rayos, menos se va a poder con R-1, R-2, etc. Es decir, podemos hacer búsqueda binaria para encontrar el menor R donde se puede.
</details>
<details>
  <summary>Hint 3</summary>
Sea K(x) = la cantidad de rayos lanzados verticalmente a la izquierda de la coordenada x inclusive. Entonces podemos verificar si es que es posible satisfacer la cota por intervalo R si es que existe solución para un sistema de inecuaciones sobre K(x) evaluado en muchos puntos. Es decir:
  <ul>
    <li>K(x) <= K(y) para todo x < y</li>
    <li>1 <= K(y - eps) - K(x + eps) <= R para todo intervalo abierto (x, y) dado en el input</li>
  </ul>
  El 'eps' es por el hecho de que justo en el extremo de un intervalo uno puede lanzar un rayo y dicho rayo no se agrega al contador del intervalo (recordar que son intervalos abiertos). Por ejemplo para este input:
<p>
5<\br>
0 5 1<\br>
5 10 1<\br>
0 4 1<\br>
4 6 1<\br>
6 10 1</p>
  la respuesta debería ser 1 (hacerse un dibujito para convencerse).
</details>
<details>
  <summary>Solución + código</summary>
  Hacemos búsqueda binaria para encontrar el R óptimo. En el predicado de la búsqueda binaria verificamos si el sistema de inecuaciones mencionados tiene solución. Para ello podemos expresar todas las desigualdades en forma canónica como var1 - var2 <= constante, armar un grafo a partir de estas desigualdades y correr bellman-ford sobre el grafo para detectar la existencia de ciclos negativos. Si no hay ciclos negativos, entonces hay solución. Para entender bien cómo funciona esto último, revisar las referencias en los comentarios del <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/UVA/558_Wormholes.cpp">Código de ejemplo</a>.
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 11](../contests#contest-11) > ```{{page.title}}```
