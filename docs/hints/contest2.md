---
title: contest 2 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```

### A - Reversed Binary Numbers
<details> 
  <summary>Hint</summary>
  Si bien en python hay funciones que entregan la representación binaria de un número, traten de construirla, recuerden los operadores bitwise vistos en la última clase.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos obtener la representación binaria de un número con operadores bitwise, por ejemplo para ver si el bit i está prendido consultamos ((N >> i) & 1), de todas formas podemos obtener la representación binaria inversa consultando siempre por el primer bit y trasladando los bits, es decir, si N = (1011) en binario, consultamos por el primer bit preguntando si es impar, en caso de estar prendido acumulamos un 1 en otra respuesta y trasladamos N a la izquierda dividiendo por 2 y la respuesta a la derecha multiplicando por 2, para N = (1011) pasaríamos a (101) y la respuesta a (10), luego N a (10) y la respuesta a (110), luego N a (1) y la respuesta a (1100) y finalmente N a (0) y respuesta a (11010), dividimos por 2 la respuesta y retornamos.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/ReversedBinaryNumbers.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/ReversedBinaryNumbers.cpp">Código de ejemplo C++</a>
</details>


<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```
