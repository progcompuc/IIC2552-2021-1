---
title: contest 6 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```

### A - Shovels and Swords
<details>
  <summary>Solución + código</summary>
  Evidentemente el resultado debe ser menor o igual a A, menor o igual a B y menor o igual a (A + B) / 3. Se puede demostrar que siempre se puede hacer igual al minimo de estas 3 cotas.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/ShovelsAndSwords.cpp">Código de ejemplo</a>
</details>

### B - Ternary String
<details> 
  <summary>Hint</summary> 
  Se puede demostrar que siempre la respuesta tendrá un bloque (>= 1) de números iguales en medio y dos distintos a cada lado. Basta con buscar el menor de estos bloques.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos iterar y acumular tamaño de bloques de números iguales, si recordamos el último número antes del bloque actual, al ver un número distinto (fin de un bloque), vemos si es distinto al número previo al bloque. En este caso este bloque nos puede servir. La respuesta es el menor de los tamaños de estos bloques + 2 (números a cada lado).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TernaryString.cpp">Código de ejemplo</a>
</details>

### C - Two Squares
<details> 
  <summary>Hint</summary>
  Basta chequear para cada vértice de cada cuadrado si está en el otro cuadrado y además chequear si el centro de cada cuadrado está en el otro cuadrado.
</details>
<details>
  <summary>Solución + código</summary>
  Como los cuadrados son paralelos a los ejes o rotados en 45 grados, podemos chequear fácilmente usando desigualdades si un punto está dentro. Usar el hint para saber que casos chequear.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TwoSquares.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```
