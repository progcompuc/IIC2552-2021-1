---
title: contest 4 - hints y códigos de ejemplo
---
[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```

### A - TROY Query
<details> 
  <summary>Hint 1</summary>
  Noten que en vez de pensar en la cantidad de veces que cada fila/columna fue actualizada para llegar a la configuración actual, sólo importa la paridad de estas actualizaciones. Es decir, si fueron updateadas una cantidad par o impar de veces.
</details>
<details> 
  <summary>Hint 2</summary>
  Si una celda es igual en ambos TROYS entonces fue actualizada una cantidad par de veces, sólo hay 2 formas de que esto pase, que su fila y columna respectivas ambas hayan sido actualizadas una cantidad par de veces o que ambas hayan sido actualizadas una cantidad impar de veces (de esta forma la suma es par). De la misma forma, si la celda marca distinto entre los TROYS, la suma debe ser impar, por lo que una debe ser impar y la otra par. Piensen en cómo llevar registro de estas implicancias de forma que sea fácil chequear en caso de una contradicción.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos registrar las implicancias como conjuntos de un Union Find. Es decir, generamos inicialmente 2 (R + C) conjuntos, dos para cada fila y columna, que representan la posibilidad de que sean par o impar. Cuando vemos el valor de una celda unimos los conjuntos correspondientes según el hint 2, de forma que conceptualmente estamos creando conjuntos de posibles valores que si pasan deben hacerlo juntos para no contradecir los registros. Si en algún momento juntamos a una fila o columna par con su misma fila o columna impar entonces tenemos una contradicción, desde ese momento en adelante la respuesta es siempre "No".
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TROYQuery.cpp">Código de ejemplo</a>
</details>

### D - K12-Bored of Suffixes and Prefixes
<details> 
  <summary>Hint</summary>
  Notemos que si mantenemos la matriz con valores correspondientes al número de cada letra (A: 1, B: 2, ...) en vez de la letra en si, la consulta que se pide es equivalente a simplemente la suma en esa región.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos mantener registro segun el Hint en un Fenwick Tree 2D. Cada update será realizar N updates a lo largo de la fila/columna correspondiente. Cada consulta será devolver la suma en esa región.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/K12-BoredOfSuffixesAndPrefixes.cpp">Código de ejemplo</a>
</details>

### E - Matrix Summation
<details> 
  <summary>Hint</summary>
  Deben ocupar directamente una de las estructuras explicadas en clase en este problema.
</details>
<details> 
  <summary>Solución + código</summary>
  Basta con ocupar directamente un Fenwick Tree 2D para sumas.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/MatrixSumation.cpp">Código de ejemplo</a>
</details>

### F - UnDetected
<details> 
  <summary>Hint</summary>
  Podemos pensar que el momento en que ya no voy a ser capaz de cruzar el campo es cuando los robots activados cubren completamente el campo en una "linea", es decir separan la mitad inferior de la superior. Deben pensar en una forma de ir actualizando una estructura para cada sensor extra que agreguen de forma de poder detectar cuando se forme una barrera rápidamente.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos pensar en N + 2 conjuntos en un Union Find, uno por cada sensor y uno para el lado izquierdo y derecho del campo. Cada vez que activamos un sensor verificamos si choca con alguno de los lados o con alguno de los sensores activos, en caso de hacerlo unimos los conjuntos correspondientes. Si en algún momento el conjunto correspondiente al borde izquierdo y al derecho son unidos, sabemos que se formó una barrera y ya no se podrá cruzar.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/UnDetected.cpp">Código de ejemplo</a>
</details>

<!-- ### H - Cut Inequality Down
<details> 
  <summary>Hint 1</summary>
  Piensen en una forma de procesar las queries en orden de tal forma que podamos realizar sólo una pasada por cada momento temporal
</details>
<details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```
