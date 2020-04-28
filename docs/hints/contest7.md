---
title: contest 7 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 7](../contests#contest-7) > ```{{page.title}}```

### C - Lucky Number Representation
<details> 
  <summary>Hint 1</summary> 
  Notemos que el problema es mucho más facil si el número es divisible por cuatro. En este caso se puede solucionar el problema dividiendo por cuatro y avanzando dígito por dígito. Si el dígito es menor o igual a seis, agregamos a esa cantidad de números un cuatro en el dígito correspondiente. Si es mayor a seis basta notar que siete cuatros es equivalente a agregar cuatro sietes por lo que agregando esto alcanzamos a rellenar lo equivalente a maximo nueve cuatros con cuatro sietes y dos cuatros, ocupando los seis espacios que tenemos. Se cumplirá que la suma de los números es igual al número original antes de ser dividido. Pero nuestro número no necesariamente es divisible por cuatro.
</details>
<details> 
  <summary>Hint 2</summary>
  Notemos además que podemos hacer un DP "naive" (ingenuo) que trate de elegir seis lucky numbers que sumen al número pedido, para esto podemos separar en estados que dependan del número a separar (N)  y en cuántos números separarlo (C), probar con todos los lucky numbers menores o iguales al número y cuando probamos el lucky number L el resultado depende del estado (N - L, C - 1). El problema de este approach es que La complejidad es muy alta, sólo es viable para números hasta 10.000 por el tiempo pedido.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos usar ambos Hints y obtener una solución. Primero descomponemos el número original N en dos partes, N1 = (N % 4000) y N2 = N - N1, evidentemente podemos resolver la solución de N1 por el DP descrito en el Hint 2. Mientras que N1 es divisible por 4 por lo que se puede obtener su solución usando el Hint 1. Luego la respuesta será los números de ambas soluciones sumados correspondientemente. Sólo hay un caso borde en que N1 no tiene solución al ser muy pequeño, acá basta con tomar N1 = (N % 4000) + 4000 y N2 = N - N1.
  <a href="">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 7](../contests#contest-7) > ```{{page.title}}```
