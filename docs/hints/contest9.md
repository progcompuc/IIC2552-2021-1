---
title: contest 9 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 9](../contests#contest-9) > ```{{page.title}}```

### A - Gluing Pictures
<details> 
  <summary>Hint 1</summary>
  Noten que basta usar un approach greedy donde vamos completando la palabra buscado usar substrings lo más grandes posibles del string grande. Esto siempre será óptimo, sólo queda saber cómo buscar el mayor substring que podemos tomar de forma eficiente.
</details>
<details> 
  <summary>Hint 2</summary>
  Podemos buscar lo descrito en el hint 1 letra por letra. Dado que hayamos precalculado el suffix array del string original, en este tendremos ordenados los sufijos. Todo substring debe ser el prefijo de un sufijo, luego basta buscar el sufijo que tenga un prefijo común más grande. Piensen cómo hacerlo letra por letra usando búsqueda binaria.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos buscar letra por letra con búsqueda binaria, inicialmente l = 0, r = N y tenemos todos los sufijos, hacemos búsqueda binaria por una letra y podemos reducir el rango a l', r' donde todos los sufijos en [l', r') comparten la primera letra con el string buscado, luego acotamos este nuevo rango según la segunda letra y así sucesivamente. En el momento donde no podamos encontrar una letra habremos encontrado el substring más largo posible, agregamos uno a la respuesta y empezamos de nuevo del rango [0, N) con la letra que quedamos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Matcomgrader/GluingPictures.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 9](../contests#contest-9) > ```{{page.title}}```
