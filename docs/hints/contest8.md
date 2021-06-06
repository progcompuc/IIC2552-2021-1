---
title: contest 8 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```

### A - Filling Shapes
<details> 
  <summary>Solución + código</summary>
  Si la cantidad de columnas es impar, es imposible rellenar, en otro caso siempre hay dos formas por cada dos columnas, luego la respuesta es 2^(N / 2).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/FillingShapes.cpp">Código de ejemplo</a>
</details>

### B - Santa Claus and Candies
<details> 
  <summary>Hint</summary>   
  La forma óptima de entregar dulces siempre será 1 al primero, 2 al segundo, ... y al último que alcances todo lo que te quede.
</details>
<details> 
  <summary>Solución + código</summary>
  La suma de 1 + 2 + ... + N = N * (N + 1) / 2, luego basta ver en qué momento esto se pasa de la cantidad de dulces que tienes y entregar el N justo antes de que se pase. Usar la estrategia del Hint para repartir.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/SantaClausAndCandies.cpp">Código de ejemplo</a>
</details>

### C - Binary Removals
<details> 
  <summary>Solución + código</summary>
  Nos piden dejar el string de la forma 000...000111...111, cómo no se pueden eliminar dígitos seguidos, el primer momento donde se vean dos 1 juntos, mientras no hayan dos 0 juntos luego de eso se podrá.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/BinaryRemovals.cpp">Código de ejemplo</a>
</details>

### D - Cormen The Best Friend Of a Man
<details> 
  <summary>Solución + código</summary>
  De forma codiciosa, si recorremos el arreglo que se nos entrega, siempre conviene aumentar el número actual al mínimo que haga que la suma del actual y el anterior sea >= K, esto llegará a la menor cantidad de adiciones.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/CormenTheBestFriendOfAMan.cpp">Código de ejemplo</a>
</details>

### E - Alternating Subsequence
<details> 
  <summary>Hint</summary>   
  Notemos que el largo más grande de una secuencia alternante es la cantidad de segmentos con números del mismo signo, pues siempre conviene tomar un número de cada segmento continuo de números del mismo signo.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando el hint, la secuencia alternante más grande y de suma mayor, toma en cada segmento de números del mismo signo al más grande de ellos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/AlternatingSubsequence.cpp">Código de ejemplo</a>
</details> 

### F - Long Jumps
<details> 
  <summary>Hint</summary>  
  Piensen en usar DP.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos hacer un dp con estado el índice en que estamos y que responda la máxima suma partiendo de este índice, luego la suma será A[i] + dp(i + A[i]), basta luego tomar el máximo de dp(i) para todo i.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/LongJumps.cpp">Código de ejemplo</a>
</details>

### G - Canine poetry
<details> 
  <summary>Hint</summary>
  Noten que basta evitar los palíndromos de tamaño 2 o 3. Pues los más grandes tienen esos en medio.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos recorrer el string y recordar las últimas 2 letras, si la letra nueva es igual a la última hay un palíndromo de tamaño 2, cambiamos la nueva, si la nueva es igual a la penúltima hay un palíndromo de tamaño 3, cambiamos la nueva. Podemos siempre asumir que la cambiamos a una letra que nunca será igual a las que vienen 3 más alla, pues hay suficientes letras en el alfabeto para eso.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/CaninePoetry.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```
