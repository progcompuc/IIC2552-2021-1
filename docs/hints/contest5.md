---
title: contest 5 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```

### A - Edges in MST
<details> 
  <summary>Hint</summary>
  En el algoritmo de kruskal para obtener el MST de un grafo, se procesan las aristas en orden de pesos y viendo la conectividad se llega siempre a la solución. La única parte en que podría haber más de una solución para un MST es si hay más de una arista con el mismo peso (y por tanto el procesamiento en kruskal es arbitrario en orden). Piensen en una forma de procesar las aristas con mismo peso simultáneamente para ver si cada una puede ser parte de una solución.
</details>
<details> 
  <summary>Solución + código</summary>
  Basta con usar el hint y simular el algoritmo de kruskal pero procesando todas las aristas del mismo peso simultáneamente. Si una arista es la única de su peso que es aceptada por kruskal, entonces está en todos los MST (any), si hay más de una aceptada del peso entonces es al menos en un MST (at least one). Si no es aceptada es none.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/EdgesInMST.cpp">Código de ejemplo</a>
</details>

### B - Tree 2
<details> 
  <summary>Hint 1</summary>
  Si supieramos cual es el nodo más lejano a nosotros, bastaría con ver si la distancia entre yo y el es mayor o igual a k, de serlo devolvemos el k-ésimo nodo en el camino y si no no existe nodo que cumpla lo pedido. Lamentablemente no podemos sacar distancias entre todos los nodos en tiempo, piensen en una forma de poder saber uno a mayor distancia rápidamente.
</details>
<details> 
  <summary>Hint 2</summary>
  Podemos obtener 2 nodos que esten lo más lejos posible uno del otro en el árbol. Basta con hacer 2 dfs ambos encontrando nodos más lejanos, el primero de un nodo cualquiera y el segundo del nodo encontrado más lejos en el primero (así encontramos el 2o). Estos dos nodos serán extremos de un diámetro de un árbol y es más, podemos demostrar que para cualquier nodo (u) en el árbol, se cumple que uno de los 2 nodos encontrados es lo más lejano a u posible. Usando esto y el hint 1 estamos casi listos. Sólo falta poder obtener distancia entre nodos y el k-ésimo en un camino rápidamente.
</details>
<details>
  <summary>Solución + código</summary>
  Para hacer lo último del hint 2 basta usar LCA, la distancia entre u y v es simplemente las profundidades de ambos nodos sumadas menos la profundidad del lca entre ellos. Para obtener el k-ésimo nodo por otro lado basta hacer binary lifting usando la información de la sparse table de ancestros en el LCA. La complejidad final de este algoritmo es O(N) por los dfs iniciales más O(Q log N) por las queries usando LCA.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Timus/Tree2.cpp">Código de ejemplo</a>
</details>

### C - Minimum spanning tree for each edge
<details> 
  <summary>Hint</summary>
  Se puede demostrar que dado un MST, para obtener el MST de un grafo forzando la aparición de una arista (e), siempre existirá una arista (f) en el MST original tal que el óptimo forzando e, es dado por MST - {f} + {e}. Luego basta encontrar el valor de esta arista f para cada arista a forzar.
</details>
<details> 
  <summary>Solución + código</summary>
  Primero encontramos un MST original y luego para cada arista (u, v) tendremos: Si estaba ya en el MST no hacemos cambies y retornamos el valor del MST original. Si no está en el MST original basta con encontrar el valor de la mayor arista en el camino entre u y v en el MST original, el valor del MST forzado será el el valor original más el de la arista forzada menos el de la encontrada en el camino. Para encontrar la mayor arista en un camino del MST basta con aplicar binary lifting en un LCA.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MinimumSpanningTreeForEachEdge.cpp">Código de ejemplo</a>
</details>

### D - Minimum Spanning Tree
<details> 
  <summary>Hint</summary>
  Problema de implementación directa de MST.
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/MST.cpp">Código de ejemplo</a>
</details>

### E - Roads in HackerLand
<details> 
  <summary>Hint 1</summary>
  Notemos que en vez de considerar el grafo completo, basta considerar el MST obtenido al usar los C_i como pesos (en vez de 2^{C_i}). Esto pues si obtenemos el MST ordenando agregando desde las aristas de menor peso, entonces cualquier arista que no esté en el MST será subóptima, pues si no fue agregada al MST, por la construcción de Kruskal debe existir un camino entre los nodos que une con sólo costos estrictamente menores. Y como en potencias de 2 distintas se cumple que la suma de potencias menores a k siempre es menor que 2^k, cualquiera de estos caminos será óptimo frente a pasar por la arista que no está en el MST.
</details>
<details> 
<summary>Hint 2</summary>
  Usando el MST del grafo, para obtener la solución tenemos que saber la suma de todas las distancias de pares de nodos en binario. Notemos que podemos obtener las veces que cada arista en el MST será usada usando un par de dfs. Primero usamos un dfs que precalcule los tamaños de cada subárbol y el segundo dfs ocupará esos valores para calcular cuantas veces se usa cada arista en el valor pedido (las veces que se usa una arista entre u y v es el tamaño del subárbol de v (S_v) multiplicado por su complemento N - S_v).
</details>
<details> 
  <summary>Solución + código</summary>
  Teniendo los valores del Hint 2 sólo queda obtener el número binario, como cada arista tiene un valor de potencia de 2 distinto, si guardamos los valores mencionados anteriormente en un arreglo indexado por las potencias C_i, podemos convertir este arreglo en la respuesta binaria acumulando hacia arriba la división por dos del valor de cada celda (dejando registrado el resto). El arreglo resultante será precisamente el número binario pedido.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/HackerRank/RoadsInHackerLand.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```
