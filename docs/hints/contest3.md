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

<!-- <details> 
  <summary>Hint</summary>
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```
