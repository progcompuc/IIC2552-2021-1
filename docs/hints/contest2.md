---
title: contest 2 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```

### B - a-Good String
<details> 
  <summary>Hint</summary>
  Notemos que podemos usar la misma definición de un string 'a'-good para calcular la minima cantidad de cambios necesarios. Primero decidimos a que lado van puras letras 'a' y luego resolvemos para el resto del string, esta decisión debe ser la que genere el mínimo incluso considerando las futuras decisiones.
</details>
<details> 
  <summary>Solución + código</summary>
  Una forma de resolver el problema es mediante una función recursiva, por ejemplo una función solve(i, j, ch) que decida la mejor forma de cambiar los caracteres entre i y j para que sea 'ch'-good, esta función debe retornar el mejor costo para ese segmento considerando 2 opciones, rellenar la primera mitad con ch y el resto cuesta solve(mid, j, ch + 1) o rellenar la segunda mitad con ch y el resto cuesta solve(i, mid, ch + 1). La complejidad total de esta solución es O(N log N), esto se puede deducir analizando por profundidad, se llega a una profundidad máxima de log N letras y cada profundidad considera entre los segmentos a todos los caracteres (N).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/AGoodString.cpp">Código de ejemplo</a>
</details>

### E - Four Segments
<details> 
  <summary>Hint</summary>   
  Consideren todas las características necesarias de los segmentos de un rectángulo.
</details>
<details> 
  <summary>Solución + código</summary>
  Hay muchas formas de resolver este problema, una es revisar que se cumplan las siguientes características: 2 segmentos verticales y 2 horizontales, cantidad de puntos totales igual a 4, todos los segmentos son distintos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/FourSegments.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```
