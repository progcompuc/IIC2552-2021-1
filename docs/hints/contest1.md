---
title: contest 1 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 1](../contests#contest-1) > ```{{page.title}}```

### B - Sum of the Others
<details> 
  <summary>Hint</summary>
  Problema bien fácil de implementación
</details>
<details> 
  <summary>Solución + código</summary>
  Al sumar todos los números en una linea podemos obtener la suma de los numeros que deberían estar a la izquierda del signo =, más el resultado de sumarlos, es decir al sumar obtenemos el doble del número que buscamos, basta dividir por dos este número.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/SumOfTheOthers.py">Solución ejemplo (Python)</a>,  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/SumOfTheOthers.cpp">Solución ejemplo (C++)</a>
</details>

### C - Maximum Square
<details> 
  <summary>Hint</summary>
  Si se fijan, para tener un cuadrado de NxN es necesario tener al menor N tablas de al menos N de largo
</details>
<details> 
  <summary>Solución + código</summary>
  Una estrategia óptima es tener los largos de las tablas ordenados de mayor a menor, de esta forma si recorremos el arreglo ordenado se tendrá que en el momento en que la cantidad de tablas restantes sea menor o igual al tamaño de la tabla siguiente ese será el largo del cuadrado óptimo (Si no lo fuera deberían haber más que esa cantidad de tablas con tamaño mayor, lo cual no es posible porque tenemos las tablas ordenadas).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MaximumSquare.py">Solución ejemplo (Python)</a>,  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MaximumSquare.cpp">Solución ejemplo (C++)</a>
</details>

### F - Center Alignment
<details> 
   <summary>Hint</summary>
   Problema bien fácil de implementación
</details>
<details>
   <summary>Solución + código</summary>
   Básicamente hay que leer todas las líneas primero, calcular el ancho máximo, y luego iterar sobre las líneas calculando el whitespace con el que hay que rellenar, y si no es divisible por 2 ir alternando entre dejar uno menos a la izquierda y derecha (se puede usar una variable booleana). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/5B_CenterAlignment.py">Solución ejemplo (Python)</a>,  <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/5B_CenterAlignment.cpp">Solución ejemplo (C++)</a>.
</details>

### H - Touchscreen Keyboard
<details> 
   <summary>Hints</summary>
   No tiene mucha ciencia, básicamente la dificultad están en saber implementarlo bien.
</details>
<details> 
  <summary>Solución + código</summary>
   Como primer paso podemos precomputar la fila y la columna de cada letra del alfabeto. Por ejemplo la letra 'q' tiene fila 0 y columna 0, mientras que la letra 'f' tiene fila 1 y columna 3. Después es fácil definir una función para calcular la distancia entre 2 strings: iteramos sobre los caracteres de forma sincronizada y calculamos la distancia manhattan entre sus posiciones (abs(fila1 - fila2) + abs(col1 - col2)) y las sumamos. Después es cosa de leer los strings del input, armar una lista de pares (distancia, palabra), ordenarlos lexicográficamente y al final imprimir. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/kattis/TouchscreenKeyboard.cpp">Código de ejemplo</a>
</details>

### I - Adding Words
<details>
  <summary> Hint </summary>
  No tiene mucha ciencia, básicamente hay que implementar las operaciones que piden. Pero hay que tener cuidado con un caso borde: cuando una variable es redefinida, ¿qué pasa con el valor antiguo que era apuntado por esa variable?
</details>
<details>
  <summary> Solución + Codigo </summary>
  Podemos guardar las variables y sus definiciones con diccionarios / maps, uno que mapee de variable a valor y otro de valor a variable. El caso borde mencionado en el hint básicamente se traduce en que al redefinir una variable, antes de redefinirla tenemos que buscar su valor antiguo y borrarlo del diccionario que mapea de valor a variable (o si no nos va a quedar un valor obsoleto que ya no es apuntado por ninguna variable). El resto es detalles de implementación. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/kattis/AddingWords.py">Solución ejemplo (Python)</a>, <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/kattis/AddingWords.cpp">Solución ejemplo (C++)</a>
</details>

### J - They are Everywhere
<details>
  <summary>Hint 1</summary>
  Básicamente tenemos una lista de letras. Ahora, pensemos en la sublista que va desde i hasta j (en Python, L[i:j+1]). ¿Cómo podemos averiguar rápidamente si es que la letra 'A' aparece en L[i:j+1]? ... piénsalo un poco antes de seguir leyendo, pero aquí un spoiler de cómo se puede hacer: como son 52 letras ('a' - 'z' y 'A' - 'Z'), podemos definir 52 arreglos del mismo largo que nuestro arreglo de letras, es decir podemos definir una matriz counts[52][largo_arreglo_letras]. Entonces, supongamos que la letra 'A' tiene índice 26, podemos hacer que counts[26][i] = la cantidad de veces que 'A' está presente en L desde la posición 0 hasta la posición i. Notar que counts[26][i] = counts[26][i-1] si L[i] no es 'A' y counts[26][i] = counts[26][i-1] + 1 si L[i] es 'A' (o sea, si en esta posición aparece 'A', le sumo 1 al contandor, y si no aparece, el contador sigue igual). Podemos hacer eso para las 52 letras. Luego es fácil saber si 'A' está presente o no entre i y j. ¿Cuántas veces aparece 'A' en ese rango? Respuesta: counts[26][j] - counts[26][i-1] (** hay que tener cuidado con el caso borde en que i justo es 0, para no salirnos del arreglo).
</details>
<details>
  <summary>Hint 2</summary>
  Supongamos que estamos parados en la posición i y nos pregunamos: ¿cuál es el primer j (j >= i) hacia la derecha a partir del cual se cumple que todas las letras aparecen entre i y j? Notar que si sabemos esa respuesta para cada i (desde 0 hasta n-1), nos quedamos con el mínimo entre todas las respuestas y ese es la respuesta al problema original, ¿verdad? Hay un detalle: la forma ingenua de hacer esto sería con 2 fors anidados, lo cual nos da una complejidad cuadrática O(n^2) y eso nos daría TLE. ¿Se puede hacer más eficiente?
</details>
<details>
  <summary>Solución + Codigo</summary>
  Precomputamos la matriz indicada por el hint 1 y luego para encontrar la respuesta al problema usamos la técnica de 2 punteros o "two pointers": tenemos un puntero i que marca el inicio del intervalo y un puntero j que marca el fin del intervalo. Tanto el i como el j siempre avanzan (ninguno retrocede, por eso la técnica es lineal, no cuadrática). Partimos con i = j = 0. Dados un i y un j fijos, saber si están todos los pokemones en el intervalo es fácil: iteramos sobre todos los pokemones que nos interesan (a lo más 52) y chequeamos si todos los contadores son positivos en el intervalo (revisar hint 1). Mientras no se cumpla la condición, avanzamos el j hacia la derecha hasta la condición se cumpla por primera vez (y ahí encontramos el óptimo para este i en específico). Luego avanzamos el i uno a la derecha. La pregunta es, ¿qué hacemos con el j ahora? Notar que no tiene sentido hacer retroceder el j: si hubiera un j más a la izquierda que le sirva al i+1, con mayor razón le habría servido al i anterior y por lo tanto el j no estaría parado donde está parado ahora. Por eso repetimos lo mismo de antes y el j nunca retrocede. La respuesta es el mínimo entre las respuestas de todos los i's. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/701C_TheyAreEverywhere.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 1](../contests#contest-1) > ```{{page.title}}```
