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

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 11](../contests#contest-11) > ```{{page.title}}```
