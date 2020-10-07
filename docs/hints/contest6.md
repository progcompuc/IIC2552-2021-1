---
title: contest 6 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```

### C - Good Travels
<details> 
  <summary>Hint</summary>
  Notemos que si en el camino óptimo que buscamos se pasa por un nodo u, siempre será posible pasar por todos los nodos en la misma componente fuertemente conexa que u. De esta forma podemos como primer paso reducir el grafo original a un grafo alterno donde cada nodo corresponde a una componente fuertemente conexa en el grafo original y sólo nos quedamos con aristas que vayan de una componente a otra. Podemos asignar valor de diversión (fun) de cada componente como la suma de la diversión de los nodos que la componen.
</details>
<details> 
  <summary>Solución + código</summary>
  Haciendo uso del hint, es conocido que el grafo resultante debe ser un DAG (directed acyclic graph). Luego podemos obtener la respuesta pedida usandoi un DP sobre el grafo construido, donde devolvemos la maxima suma de diversiones en un camino de componentes que termine en la componente que corresponda a la ciudad de destino.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/GoodTravels.cpp">Código de ejemplo</a>
</details>

### D - Hegde Mazes
<details> 
  <summary>Hint</summary>
  Si sólo existe un camino simple que une S y T entonces removiendo cualquier arista en el camino los nodos S y T quedarán desconectados, es decir, todas las aristas del camino que buscamos deben ser aristas de corte.
</details>
<details> 
  <summary>Solución + código</summary>
  Basta saber si existe un camino entre S y T que use sólo aristas de corte, para esto podemos usar Union Find uniendo dos nodos si hay una arista de corte entre ellos. Luego la respuesta es si los nodos estan unidos en el union find o no.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/URI/HedgeMazes.cpp">Código de ejemplo</a>
</details>

### E - Necklace
<details> 
  <summary>Hint</summary>
  Siempre que haya un camino donde todas las aristas no sean de corte, se podrá construir un necklace, esto pues al no ser de corte existe otro camino que completa el ciclo.
</details>
<details> 
  <summary>Solución + código</summary>
  Basta con encontrar y remover las aristas de corte y ver si después de ese proceso aún hay un camino entre S y T.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/ICPC/Necklace.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```
