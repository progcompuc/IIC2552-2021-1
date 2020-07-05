---
title: contest 13 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 13](../contests#contest-13) > ```{{page.title}}```

### B - Billiard
<details> 
  <summary>Hint 1</summary>
  En primer lugar, si la dirección es paralela a algún eje la respuesta se puede obtener chequeando las coordenadas directamente. Notemos que en el resto de los casos podemos considerar que la dirección de la bola siempre será de 45 grados subiendo, de lo contrario podemos rotar la tabla para que sea así.
</details>
<details> 
  <summary>Hint 2</summary>
  Imaginemos, en vez de una bola rebotando, que tenemos una teselación infinita del plano con tablas de N x M. De esta forma un lanzamiento de la bola se puede ver como una recta en esta teselación y si en su camino hay un punto de la forma (k1 * N, k2 * M) entonces cae en un agujero de la tabla.
  
  Usando el hint 1 asumimos que la bola sólo sube en 45 grados. Denominemos rx como la distancia de la coordenada x inicial a N, y ry a la distancia en el eje y a M. Cualquier punto en la recta que transita la bola será de la forma (x, y) + (d, d). Luego para llegar a un punto de la forma (k1 * N, k2 * M) se necesita que exista d tal que d = rx (mod N) y, d = ry (mod M), de lo contrario será imposible que x + d = 0 (mod N) y, x + d = 0 (mod M) al mismo tiempo.
</details>
<details> 
  <summary>Solución + código</summary>
  Para encontrar un d como descrito en el hint 2 basta usar CRT para las ecuaciones d = rx (mod N) y, d = ry (mod M). Si ha solución entonces podemos obtener las constantes k1 y k2 de (k1 * N, k2 * M) como (d - rx) / N y (d - ry) / M respectivamente. Luego obtenemos el agujero en que cae con argumentos de rotación y paridad.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Billiard.cpp">Código antiguo del ayudante (cuando usaba templates)</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 13](../contests#contest-13) > ```{{page.title}}```
