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
  Notemos además que podemos hacer un DP "naive" (ingenuo) que trate de elegir seis lucky numbers que sumen al número pedido, para esto podemos separar en estados que dependan del número a separar (N)  y en cuántos números separarlo (C), probar con todos los lucky numbers menores o iguales al número y cuando probamos el lucky number L el resultado depende del estado (N - L, C - 1). La respuesta estará dada por DP(N, 6), con N el número incial. El problema de este approach es que La complejidad es muy alta, sólo es viable para números hasta 10.000 por el tiempo pedido.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos usar ambos Hints y obtener una solución. Primero descomponemos el número original N en dos partes, N1 = (N % 4000) y N2 = N - N1, evidentemente podemos resolver la solución de N1 por el DP descrito en el Hint 2. Mientras que N1 es divisible por 4 por lo que se puede obtener su solución usando el Hint 1. Luego la respuesta será los números de ambas soluciones sumados correspondientemente. Sólo hay un caso borde en que N1 no tiene solución al ser muy pequeño, acá basta con tomar N1 = (N % 4000) + 4000 y N2 = N - N1.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/LuckyNumberRepresentation.cpp">Código de ejemplo</a>
</details>

### Gates of uncertainty
<details> 
  <summary>Hint</summary> 
  Notar que el output de correcto o equivocado de la salida en uno de los nodos depende únicamente del output y correctitud del mismo en los nodos de input. De esta forma podemos separar el problema en nodos. Por ejemplo si ambos nodos input tienen salidas correctas y el nodo en cuestión funciona bien, el output será correcto. Por otro lado si uno de los nodos inputs tiene un cero correcto yo soy capaz de generar un uno correcto (a menos de que el nodo esté fijo en 0).
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos construir un DP que dependa de 3 cosas, nodo, output generado (a) y output correcto (b) y que nos cuente cuantas combinaciones del input (la parte que afecta a este nodo) generan a en el nodo cuando deberían generar b. Para esto podemos ocupar el hint y hacer un dp que sólo dependa de las combinaciones de output y output correcto de los nodos input del nodo. Hay 4 combinaciones para cada nodo de input por lo que el dp en un nodo depende de 16 combinaciones de sus nodos input, las que se separan en aportar a las distintas posibilidades de a y b (y si el nodo esta defectuoso). Traten de ver qué combinaciones de los inputs aportan a cada combinación de a y b en el nodo, y armar el DP a base de esa dependencia. La complejidad total de esta solucion es O(100000 * 2 * 2 * 16) donde 100000 * 2 * 2 sale de la cantidad de estados y 16 de la  máxima cantidad de subestados de los que depende un estado.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/GatesOfUncertainty.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 7](../contests#contest-7) > ```{{page.title}}```
