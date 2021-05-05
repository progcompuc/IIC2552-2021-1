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

### D - Hanoi Towers Trouble Again!
<details> 
  <summary>Hint</summary>
  Se puede programar un backtracking que solucione el problema.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos hacer un backtracking solve(i, x) que busca poner x en alguno de los primeros i - 1stacks, si se puede en alguno intentamos y se sigue con x + 1 en los primeros i - 1, si no se puede lo ponemos en el i-ésimo y seguimos con el x + 1 en los primeros i stacks. Cuando intentemos un i mayor al permitido cortamos.
  <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/UVA/10276_HanoiTowerTroublesAgain!.cpp">Código de ejemplo</a>
</details>

### E - Johnny and His Hobbies
<details> 
  <summary>Solución + código</summary>
  Podemos probar con todos los números k del 1 al 1024 y ver que set de números nos genera, al primer momento donde los sets sean iguales, retornamos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/JohnnyAndHisHobbies.cpp">Código de ejemplo</a>
</details>

### F - Berland Regional
<details>
  <summary>Hint</summary>
  La cantidad de universidades con al menos K personas será <= piso de N / K. La suma de piso(N / K) desde K = 1 hasta N, es del orden O(N log(N)).
</details>
<details> 
  <summary>Solución + código</summary>
  Para cada K basta con sumar sobre todas las universidades con al menos K estudiantes (se suma el acumulado hasta N_u - N_u % K). Usando el hint sabemos que en total revisaremos orden NlogN universidades entre todos los K. Para no volver a revisar una universidad, una vez que se le revise para su número máximo de estudiantes, se puede eliminar del arreglo de universidades que revisamos (más eficiente hacerlo con un set de índices de universidades a seguir revisando).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/BerlandRegional.cpp">Código de ejemplo</a>
</details>

### G - Songs Compression
<details>
  <summary>Hint</summary>
  Siempre conviene reducir lo más posible el tamaño, comprimiendo aquella canción que se reduzca más.
</details>
<details> 
  <summary>Solución + código</summary>
  Si ordenamos las canciones desde la que más se reduce a la que menos, basta iterar sobre este orden hasta que el tamaño ocupado sea menor o igual al pedido.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/SongsCompression.cpp">Código de ejemplo</a>
</details>

### H - AGAGA XOOORRR
<details>
  <summary>Hint</summary>
  Como cada operación toma dos números contiguos, podemos reducir el problema a encontrar una partición en segmentos en el arreglo cuyo xor sea igual. Es más, esto se puede reducir a dos casos, encontrar una división en 2 del arreglo donde cada parte tenga XOR iguales, o una división en 3 del arreglo con la misma propiedad.
</details>
<details> 
  <summary>Solución + código</summary>
  Como el XOR es asociativo, podemos calcular un arreglo de XOR acumulado en el arreglo, es decir, calcular un arreglo X tal que X[i] tenga el XOR de los primeros i valores de A. Usando el hint, para chequear el primer caso (2 segmentos), podemos iterar sobre el arreglo y ver si A[0:i] y A[i:N] tienen el mismo XOR (Usar X para calcular esto rápidamente). Podemos usar la misma estrategia para el segundo caso (3 segmentos), revisar para cada j>i si A[0:i], A[i:j], A[j:N] tienen el mismo XOR. Si alguna de estas cosas se cumple la respuesta es YES.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/AGAGAXOOORRR.cpp">Código de ejemplo</a>
</details>

<!-- <details>
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```
