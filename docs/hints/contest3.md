---
title: contest 3 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```

### A - Busqueda Binaria
<details> 
  <summary>Solución + código</summary>
  Implementación 101 de búsqueda binaria lower bound, pueden buscar ejemplos de implementación adicional en materiales del curso.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/BusquedaBinaria.py">Código de ejemplo Python</a>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/BusquedaBinaria.cpp">Código de ejemplo C++</a>
</details>

### B - Busqueda Binaria 2
<details> 
  <summary>Solución + código</summary>
  Implementación 101 de búsqueda binaria upper bound, pueden buscar ejemplos de implementación adicional en materiales del curso.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/BusquedaBinaria2.py">Código de ejemplo Python</a>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/BusquedaBinaria2.cpp">Código de ejemplo C++</a>
</details>

### C - Berland Collider
<details> 
  <summary>Hint</summary>
  Deben hacer búsqueda binaria decimal en el tiempo, para esto deben poder checkear dado un tiempo si es que ha habido un choque hasta ese momento. Piensen en cómo chequear eso.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando el hint, podemos checkear si ha habido un choque en el tiempo t recorriendo el arreglo ordenado de posiciones de izquierda a derecha y calculando las nuevas posiciones usando la fórmula x[i] + v[i] * t, si recordamos al recorrer el arreglo la partícula que se mueve hacia la derecha que ha llegado más lejos y nos encontramos con una partícula que va hacia la izquierda que queda antes que la partícula recordada entonces tuvo que haber habido un choque. Usando este predicado en la búsqueda binaria encuentran el resultado. OJO que en este problema es necesario usar c++ por lo ajustado del tiempo límite.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/BerlandCollider.cpp">Código de ejemplo</a>
</details>

### D - Vanya and Lanterns
<details> 
  <summary>Hint</summary>
  Si usamos búsqueda binaria para encontrar el radio pedido, debemos pensar en un predicado que dado un radio nos diga si es suficiente para cubrir el camino o no. Pueden chequear esto linealmente recorriendo las lámparas y marcando recordando la máxima coordenada iluminada hacia la derecha, si en algún punto el radio hacia la izquierda no alcanza la coordenada recordada hasta el paso anterior, entonces no cubre todo el camino. Ojo con que la coordenada recordada empieza siendo 0 y que al final deben chequear que se llegue al largo final del camino.
</details>
<details> 
  <summary>Solución + código</summary>
  Basta implementar búsqueda binaria con el predicado explicado en el hint.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/VanyaAndLanterns.py">Código de ejemplo Python</a>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/VanyaAndLanterns.cpp">Código de ejemplo C++</a>
</details>

### E - Need for Speed
<details> 
  <summary>Hint</summary>
  Si usamos búsqueda binaria para encontrar el c pedido, debemos pensar en un predicado que dado un c nos diga si el tiempo que toma es menor o no al tiempo que sabemos que demora el camino. En caso de ser menor necesitamos un c más pequeño y viceversa. Piensen en cómo calculan el tiempo que demoraría el camino dado un c.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando el hint necesitamos poder calcular el tiempo que tomaría el camino dado un valor para c. Para esto basta saber que distancia = velocidad * tiempo, luego podemos obtener el tiempo sumando distancia / velocidad para cada tramo donde la velocidad será (v[i] + c). Usando este valor como dice el hint en una búsqueda binaria encontramos la respuesta.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/NeedForSpeed.py">Código de ejemplo Python</a>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/NeedForSpeed.cpp">Código de ejemplo C++</a>
</details>

### F - The Meeting Place Cannot Be Changed
<details> 
  <summary>Hint</summary>
  Si usamos búsqueda binaria para poder calcular el menor tiempo necesario para juntarse, debemos generar un predicado que dado un tiempo t nos diga si es posible juntarse o no en ese tiempo. Para esto usen que cada persona i en un tiempo t puede llegar a cualquier punto en un rango (x[i] - v[i] * t, x[i] + v[i] * t).
</details>
<details> 
  <summary>Solución + código</summary>
  Usando el hint, podemos verificar si es posible juntarse en un tiempo te viendo si los rangos de cada persona tienen intersección no vacía, para esto basta recordar el máximo límite inferior L de los rangos y el mínimo límite superior R de los rangos, si L <= R entonces si hay intersección. Usando este predicado en una búsqueda binaria se encuentra la respuesta.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TheMeetingPlaceCannotBeChanged.py">Código de ejemplo Python</a>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TheMeetingPlaceCannotBeChanged.cpp">Código de ejemplo C++</a>
</details>

### G - Distributing Ballot Boxes
<details> 
  <summary>Hint</summary>
  Nos preguntan por la cantidad de personas asignadas a la caja con más personas, en la distribución más eficiente posible. LLamemos a este valor óptimo X*. ¿Qué implica esto? Que no es posible hacerlo mejor que X*. Es decir, no es posible distribuir personas en las cajas de tal manera que la caja con más personas tenga estrictamente menos de X* personas. Cualquier otra distribución tendrá un máximo de X >= X*. En otras palabras, si nos preguntamos: ¿Es posible distribuir personas en las cajas de tal manera que la caja con más personas no se pase de X? la respuesta a esta pregunta es NO para X < X* y es sí para X >= X* ... eureka moment (?) ... podemos usar búsqueda binaria para encontrar X* !!
</details>
<details> 
  <summary>Solución + código</summary>
  Simplemente usamos búsqueda binaria para encotrar el primer X que responde sí a la pregunta del hint. ¿Cómo implementamos la pregunta? Dado un X, queremos saber si es posible asignar personas a las cajas de tal manera que la caja con más personas no se pase de X. Este predicado es fácil de implementar: por cada ciudad dividimos su población por X (redondeando hacia arriba) y ese es el mínimo número de cajas necesarias para dicha ciudad. Si sumamos todo esto y nos pasamos de la cantidad de cajas disponibles, no se puede, de lo contrario, sí se puede.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/DistributingBallotBoxes.py">Código de ejemplo Python</a>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/DistributingBallotBoxes.cpp">Código de ejemplo C++</a>
</details>
  
### H - Freight Train
<details> 
  <summary>Hint</summary>
  Similar al problema G, podemos pensar en una cota superior X para el tren más largo que enviamos a Luxemburgo. Si el óptimo es X*, entonces para X < X* no se puede y para X >= X* sí se puede, entonces podemos encontrar X* haciendo búsqueda binaria.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos búsqueda binaria para encontrar X*. Dado una cota superior X, debemos verificar si es posible enviar los vagones con freight a Luxemburgo sin que el tren más largo se pase de X vagones. Eso lo podemos chequear de forma codiciosa: partimos con un tren de largo X que se agarra los primeros X vagones, si alguno de ellos contiene freight, se envía a luxemburgo. Si ningún vagón tenía freight, alargamos el tren lo máximo posible con vagones vacíos y lo enviamos a Netherlands, y repetimos el proceso con lo que va quedando. Si la cantidad de trenes necesarios para hacer eso se pasa de L, no se puede, de lo contrario, sí se puede.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/FreightTrain.py">Código de ejemplo Python</a>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/FreightTrain.cpp">Código de ejemplo C++</a>
</details>

### I - Frets On Fire
<details> 
  <summary>Solución + código</summary>
  Pueden revisar la editorial donde se encontraba este problema en 
  <a href="https://codeforces.com/blog/entry/66411">Codeforces</a>.
  Es el problema D en ese link.
</details>


<!-- <details> 
  <summary>Hint</summary>
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```
