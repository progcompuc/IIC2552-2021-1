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

### The Meeting Place Cannot Be Changed
<details> 
  <summary>Hint</summary>
  Si usamos búsqueda binaria para poder calcular el menor tiempo necesario para juntarse, debemos generar un predicado que dado un tiempo t nos diga si es posible juntarse o no en ese tiempo. Para esto usen que cada persona i en un tiempo t puede llegar a cualquier punto en un rango (x[i] - v[i] * t, x[i] + v[i] * t).
</details>
<details>
  Usando el hint, podemos verificar si es posible juntarse en un tiempo te viendo si los rangos de cada persona tienen intersección no vacía, para esto basta recordar el máximo límite inferior L de los rangos y el mínimo límite superior R de los rangos, si L <= R entonces si hay intersección. Usando este predicado en una búsqueda binaria se encuentra la respuesta.
  
  <summary>Solución + código</summary>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TheMeetingPlaceCannotBeChanged.py">Código de ejemplo Python</a>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TheMeetingPlaceCannotBeChanged.cpp">Código de ejemplo C++</a>
</details>

<!-- <details> 
  <summary>Hint</summary>
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```
