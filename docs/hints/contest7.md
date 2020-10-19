---
title: contest 7 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 7](../contests#contest-7) > ```{{page.title}}```

### A - In Case of an Invasion, Please...
<details> 
  <summary>Hint 1</summary>
  Intenten una búsqueda binaria sobre la respuesta.
</details>
<details> 
  <summary>Hint 2</summary> 
  En la búsqueda binaria, dado un tiempo tratamos de ver si la respuesta es posible con un problema de flujo máximo, para eso podemos intentar unir lugares a refugios si es posible llegar a ellos en el tiempo, es posible saber si es posible ir a cada refugio en el tiempo sin empeorar la complejidad preprocesando las distancias a los refugios con un Dijkstra.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando los hints anteriores la solución consiste en hacer búsqueda binaria sobre la respuesta y para checkear generamos un grafo para flujo máximo tirando aristas de la fuente a los nodos con su capacidad entregada in aristas de capacidad infinita de los nodos a los refugios que se alcancen en el tiempo de la búsqueda según el dijkstra preprocesado. Si el flujo es igual a la cantidad de personas totales se aprueba la condición. Sin embargo para que pase en tiempo se necesita una optimización extra uniendo aquellas posiciones que pueden llegar a los mismos refugios.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/InCaseOfInvasion.cpp">Código de ejemplo</a>
</details>

### B - Surely You Congest
<details> 
  <summary>Hint 1</summary>
  Se puede observar que si dos lugares tienen distancias mínimas al destino distintas entonces no hay forma de que choquen en el camino si van sólo por caminos óptimos.
</details>
<details> 
  <summary>Hint 2</summary>
  Dado que tengamos las distancias al destino precalculadas (con un algoritmo como dijkstra), podemos asegurarnos de usar sólo aristas que sean óptimas usando aquellas que mantengan distancias óptimas del dijkstra a traves de ellas. A esta técnica se le conoce como usar el DAG de caminos óptimos.
</details>
<details> 
  <summary>Solución + código</summary>
  Por el hint 1, podemos procesar las posiciones por distancia al destino pero procesando los que esten a distancias iguales al mismo tiempo, para saber cuantas personas pueden llegar a destino de las que se procesan en algún momento podemos plantear un problema de flujo máximo, podemos tirar aristas de flujo 1 a todas las posiciones que tengan misma distancia (1 por cada persona en ellas) además usamos aristas de capacidad 1 en los caminos óptimos del hint 2. A la respuesta se le suma el flujo máximo en cada procesamiento.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/SurelyYouCongest.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 7](../contests#contest-7) > ```{{page.title}}```
