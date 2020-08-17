---
title: contest 1 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 1](../contests#contest-1) > ```{{page.title}}```

### B - Roadwork
<details> 
  <summary>Hint 1</summary>
  Para facilitar el análisis, en vez de pensar para cada persona con qué obstáculo choca, lo podemos ver como para cada obstáculo, qué personas detiene.
  Podemos ver que el obtáculo en X entre S y T detiene a la persona que parte en D si S - X <= D < T - X.
</details>
<details> 
  <summary>Hint 2</summary>
  Si analizamos los obstáculos y las personas en orden temporal (obstáculos tomando tiempo entre los que si una persona sale choca con el) y llevamos cuenta de los intervalos activos, podemos responder la distancia que caminará (en caso de parar) si mantenemos la posición de los obstáculos en una estructura ordenada.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos generar un vector de eventos temporales el cual recorreremos en orden, los eventos pueden ser, empieza el efecto de un obstáculo (S - X como en Hint 1), termina el efecto de un obstáculo y sale una persona. Al recorrer el vector, basta mantener un multiset ordenado con la posición de los obstáculos que estén activos para poder responder la distancia caminada para cada persona en O(1) cuando salga el evento correspondiente y con updates en O(log N) al empezar o terminar alguno.
  La complejidad total de esta solución es O((N + Q) log(N + Q))
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/AtCoder/Roadwork.cpp">Solución ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 1](../contests#contest-1) > ```{{page.title}}```
