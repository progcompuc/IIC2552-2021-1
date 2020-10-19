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

### E - Domino Art
<details> 
  <summary>Hint</summary>
  Notemos que si coloreamos las celdas del tablero como ajedrez, una pieza de dominó siempre une celdas de colores opuestos, luego si existe una forma de cubrir con dominos entonces todas las celdas de color negro debe poder conectarse a una blanca sin traslapar.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando el hint podemos chequear la existencia de un cubrimiento con un problema de flujo donde unimos a la fuente las celdas de color negro con capacidad 1, luego unimos las celdas negras que nos importan a las blancas que nos importan adyacentes, luego unimos las blancas que nos importan al destino con capacidad uno, si el flujo es igual a la mitad de las celdas que nos importan entonces es posible cubrir la figura.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Otros/DominoArt.cpp">Código de ejemplo</a>
</details>

### F - Kill the Werewolf
<details> 
  <summary>Hint 1</summary>
  Piensen en como contar los que no tienen oportunidad de ganar en vez de los que si la tengan
</details>
<details> 
  <summary>Hint 2</summary>
  Supongamos que analizamos las posibilidades de la i-ésima persona, suponinendo que todos los que la eligieron en primera fase votan por ella en 2a fase, la única forma de ganar es que con los otros votos mas el de la i-ésima persona haya alguien que acumule al menos tantos votos como la i-ésima. Luego para que no tenga oportunidad debe haber una forma de repartir los votos en que nadie llegue al límite de la cantidad de votos que recibe la i-ésima persona.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando los hints se analiza la posibilidad de cada persona 1 a 1, para chequear generamos un grafo bipartito con 2 nodos por persona para flujo máximo, unimos las personas que no eligieron a la i-ésima en primera fase con sus posibles votos. le damos capacidad 1 a todas las aristas de la fuente y de los posibles votos pero ajustamos las capacidades al destino para impedir que se pueda tener más o igual votos que los que tendrá la i-ésima persona. Si el flujo máximo es igual a la gente considerada en el grafo es porque pueden impedir que la i-ésima persona gane.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/URI/KillTheWerewolf.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 7](../contests#contest-7) > ```{{page.title}}```
