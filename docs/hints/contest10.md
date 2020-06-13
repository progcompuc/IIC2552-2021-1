---
title: contest 10 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 10](../contests#contest-10) > ```{{page.title}}```

### A - The Labyrinth
<details>
  <summary>Hint</summary> 
  Los puntos forman "componentes conexas". Si un aterisco se convierte en punto, entonces se va a fusionar con todas las componentes conexas de puntos adyacentes a él. De hecho, si tenemos 2 o más componentes conexas de puntos separadas por un aterisco, al convertir el asterisco en punto esas dos componentes se van a fusionar en una pura gran componente.
</details>
<details> 
  <summary>Solución + código</summary>
  Usamos DFS o BFS para identificar todas las componentes conexas de puntos en el tablero original. Cada punto lo reemplazados por el ID de su componente conexa. Además, por cada componente conexa guardamos su tamaño. Después iteramos sobre todas las celdas asterisco y vemos todas las compontentes conexas adyacentes (vemos todos los IDs distintos adyacentes en el tablero), y sumamos los tamaños + 1. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/616C_TheLabyrinth.cpp">Código de ejemplo</a>
</details>

### D - Geophysics Prospection
<details>
  <summary>Hint</summary> 
  Para poder contar agrupaciones de elementos iguales podemos usar un dfs que cuente los elementos de cada componente, si hacemos un dfs en cada componente que pase su tamaño sólo debemos ordenar para obtener la respuesta. Para esto hay que tener cuidado de no repetir necesariamente los dfs que se realizan.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos hacer dfs al estilo contar componentes conexas, vamos por cada celda, si no la hemos visitado hacemos un dfs que sólo recorrerá celdas de ese tipo y guardamos el tamaño que recorre, y seguimos así. Al final basta con encontrar alguna manera de ordenar los tamaños obtenidos para devolver como se pide. Una opción es hacer uso de priority queues para cada tipo de material.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/ICPC/GeophysicsProspection.cpp">Código de ejemplo</a>
</details>

### F - Substring
<details> 
  <summary>Hint 1</summary>
  Notemos que si el gráfico contiene algún ciclo, necesariamente la resupuesta será -1. Por otro lado, si tuvieramos la certeza de que el grafo es acíclico podríamos hacer uso de un dp para obtener la solución.
</details>
<details> 
  <summary>Hint 2</summary>
  Este dp puede ser por ejemplo contar la cantidad de letras de un tipo C máximas que se pueden obtener para caminos que terminan en el nodo U. Este dp sólo dependería del mismo para los nodos que tienen aristas que llegan a U sumado 1 si la letra asociada a U es C.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución consiste simplemente en primero chequear la existencia de un ciclo en el grafo, si hay ciclo respondemos -1 por el hint 1, de lo contrario procedemos con el approach presentado en el hint 2. Para chequear la existencia de un ciclo basta realizar un dfs, si en algún momento durante la búsqueda se trata de volver a un nodo ya visitado que esté activo (Sea ancestro del nodo que estamos viendo en la búsqueda), entonces tendremos un ciclo. Para saber qué nodos están activos basta tener un arreglo booleano en el cual activamos la posición de un nodo al principio de su llamada en el dfs y la apagamos al final.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Substring.cpp">Código de ejemplo</a>
</details>

### G - Galaxy Collision
<details> 
  <summary>Hint</summary>
  Para empezar, debemos obtener un grafo que poder trabajar. Una opción es unir aquellas estrellas cuya distancia es menor a 5 años luz, para eso basta tener un map asociando las posiciones de las estrellas a su índice y para cada estrella ver si las posiciones a menos de 5 años luz tienen alguna estrella, en caso de haber una estrella unimos. De esta forma obtenemos el grafo que queríamos.
</details>
<details> 
  <summary>Solución + código</summary>
  Finalmente, para obtener la solución al problema basta realizar un dfs por cada componente del grafo generado. Los vértices que visitamos a profundida par y los que visitamos a profundidad impar en cada componente deben ser parte de galaxias distintas. Luego la respuesta final corresponde a la suma de los tamaños del menor entre cantidad de estrellas a profundidad par o impar en cada componente.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/URI/GalaxyCollision.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 10](../contests#contest-10) > ```{{page.title}}```
