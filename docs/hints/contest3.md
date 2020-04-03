---
title: contest 3 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```

### A - Busqueda Binaria
<details> 
  <summary>Hint</summary>
  Hello world de búsqueda binaria
</details>
<details> 
  <summary>Solución + código</summary>
  Simplemente aplicar búsqueda binaria. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/BBIN_BusquedaBinaria.cpp">Código de ejemplo</a>
</details>

### B - Búsqueda Binaria 2
<details> 
  <summary>Hint</summary>
  Hello world de búsqueda binaria
</details>
<details> 
  <summary>Solución + código</summary>
  Simplemente aplicar búsqueda binaria. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/BBIN2_BúsquedaBinaria2.cpp">Código de ejemplo</a>
</details>

### C - Berland Collider
<details> 
  <summary>Hint</summary>
  Para verificar si un tiempo fijo es suficiente para que exista un choque basta fijarse en que para cada partícula moviendose a la izquierda todas las partículas que estaban originalmente a su izquierda moviendose hacia la derecha sigan a su izquierda. O viceversa.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando lo expresado en el hint, podemos realizar búsqueda binaria sobre el tiempo necesario para que haya un choque de forma que para chequear si un tiempo determinado es suficiente recorremos el arreglo ordenado de posiciones guardando la mayor posición de las partículas que se mueven a la derecha en el tiempo actual. Si en algún momento mientras recorremos el arreglo la nueva posición de una partícula moviéndose a la izquierda es menor que la mayor acumulada de las que se mueven a la derecha, tendremos un choque.
  
  Ojo que en este problema los límites de tiempo son bastante acotados, por lo que recomendamos usar C++ para programar la solución usando los comandos ios::sync_with_stdio(0); cin.tie(0); para obtener manejo mas rápido de input y output.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/BerlandCollider.cpp">Código de ejemplo</a>
</details>

### D - Vanya and Lanterns 
<details> 
  <summary>Hint</summary>
  Para verificar si un radio sirve para cubrir la calle entera basta con recorrer las posiciones de forma ordenada y checkear que alcance a cubrir todos los espacios entre linternas y a los bordes.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos hacer búsqueda binaria sobre el radio óptimo, para eso podemos inicializar los límites de la búsqueda como mínimo 0 y máximo 10^9 y en cada iteración revisar si la mitad del rango alcanza a cubrir la calle, para verificar procedemos como en el hint, como en cada iteración el rango se divide a la mitad con 1000 iteraciones tendremos más que suficiente para alcanzar la precisión pedida.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/VanyaAndLanterns.cpp">Código de ejemplo</a>
</details>

### E - Need for Speed 
<details> 
  <summary>Hint</summary>
  Podemos abordar el problema como una búsqueda binaria sobre los posibles valores de la constante, piensen en cómo seria posible ocupar el tiempo real.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos como dice el hint hacer una búsqueda binaria sobre los posibles valores de la constante, para esto primero obtenemos los límites de sus posibles valores, la constante va a ser como mínimo el valor que hace a todas las entradas positivas y como máximo 2*10^6, para cada posible valor de la constante durante la búsqueda binaria obtenemos su tiempo dado como la suma de las distancias dividido en sus velocidades trasladadas.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/NeedForSpeed.cpp">Código de ejemplo</a>
</details>

### F - The Meeting Place Cannot Be Changed
<details> 
  <summary>Hint</summary>
  Si un tiempo determinado es suficiente para juntarse, entonces la menor de las máximas posiciones que alcanzan los jugadores en ese tiempo es mayor o igual a la mayor de las mínimas posiciones.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos usar lo mencionado en el hint para hacer una búsqueda binaria sobre el tiempo necesario para juntarse, usando el que el tiempo sea sufuciente como predicado de la búsqueda.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TheMeetingPlaceCannotBeChanged.cpp">Código de ejemplo</a>
</details>

### G - Distributing Ballot Boxes
<details> 
  <summary>Hint</summary>
  Nos preguntan por la cantidad de personas asignadas a la caja con más personas, en la distribución más eficiente posible. LLamemos a este valor óptimo X*. ¿Qué implica esto? Que no es posible hacerlo mejor que X*. Es decir, no es posible distribuir personas en las cajas de tal manera que la caja con más personas tengo estrictamente menos de X* personas. Cualquier otra distribución tendrá un máximo de X >= X*. En otras palabras, si nos preguntamos: ¿Es posible distribuir personas en las cajas de tal manera que la caja con más personas no se pase de X? la respuesta a esta pregunta es NO para X < X* y es sí para X >= X* ... eureka moment (?) ... podemos usar búsqueda binaria para encontrar X* !!
</details>
<details> 
  <summary>Solución + código</summary>
  Simplemente usamos búsqueda binaria para encotrar el primer X que responde sí a la pregunta del hint. ¿Cómo implementamos la pregunta? Dado un X, queremos saber si es posible asignar personas a las cajas de tal manera que la caja con más personas no se pase de X. Este predicado es fácil de implementar: por cada ciudad dividimos su población por X (redondeando hacia arriba) y ese es el mínimo número de cajas necesarias. Si sumamos todo esto y nos pasamos de la cantidad de cajas disponibles, no se puede, de lo contrario, sí se puede. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/LiveArchive/5822_DistributingBallotBoxes_v2.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```
