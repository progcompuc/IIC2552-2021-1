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

### B - Two distinct points
<details> 
  <summary>Hint</summary>
  Basta con elegir un número cualquiera del primer segmento y para el segundo elegir alguno de los vértices, mientras sea distinto al punto elegido para el primer segmento.
</details>
<details> 
  <summary>Solución + código</summary>
  Implementar el hint.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TwoDistinctPoints.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TwoDistinctPoints.cpp">Código de ejemplo C++</a>
</details>

### C - Polynomial Multiplication I
<details> 
  <summary>Hint</summary>
  Multiplicar polinomios en O(N^2) pasa en tiempo, es decir, multipliquen coeficiente a coeficiente.
</details>
<details> 
  <summary>Solución + código</summary>
  Para multiplicar polinomios basta hacer un doble for en los grados de cada polinomio y multiplicar cada coefs_1[i] * coefs_2[j] asignando la respuesta a coefs_ans[i + j].
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/PolynomialMultiplication.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/PolynomialMultiplication.cpp">Código de ejemplo C++</a>
</details>

### D - Remove Smallest
<details> 
  <summary>Hint</summary>
  Piensen en cómo lo harían si el arreglo estuviera ordenado de mayor a menor.
</details>
<details> 
  <summary>Solución + código</summary>
  Si primero ordenamos el arreglo, tendremos que los elementos que buscamos estarán en índices continuos, luego podemos recorrer el arreglo de izquierda a derecha y cada vez que nos encontremos con un salto de más de 1 con el elemento anterior, tendremos que ese elemento (el anterior) no puede ser eliminado y sumamos 1 a la respuesta.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/RemoveSmallest.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/RemoveSmallest.cpp">Código de ejemplo C++</a>
</details>

### E - Counting Stars
<details> 
  <summary>Hint</summary>
  Podemos recorrer todas las posiciones, cada vez que nos encontremos con una estrella (con un '-') debemos marcar todo lo perteneciente a esa estrella para no contarla denuevo, piensen en cómo hacer eso.
</details>
<details> 
  <summary>Solución + código</summary>
  Cada vez que nos encontramos una estrella podemos llamar una función recursiva que visite toda la estrella y la marque como contada, para esto la función puede recibir coordenada x e y y llamar recursivamente a la misma función para los vecinos de la coordenada que también sean parte de la estrella y no hayan sido ya visitados por la función luego sólo sumamos uno a la respuesta cada vez que veamos un '-' no marcado como visitado y cada vez que pase llamamos a la función recursiva para marcar como visitada toda esa estrella. Esta técnica de visitar es una aplicación de recorrer grafos con dfs, lo que se verá más adelante.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/CountingStars.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/CountingStars.cpp">Código de ejemplo C++</a>
</details>

### F - Pizza Hawaii
<details> 
  <summary>Hint</summary>
  Podemos guardar en diccionarios/maps para cada ingrediente en qué recetas aparece.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando el hint basta comparar cada par de ingredientes (uno de cada idioma) y ver si las listas de recetas en que aparecen son iguales. En caso de serlo agregamos ese par a la respuesta. Para devolver los pares en el orden pedido basta hacer un sort a la lista de pares respuesta.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/PizzaHawaii.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/PizzaHawaii.cpp">Código de ejemplo C++</a>
</details>

### G - Zagrade
<details> 
  <summary>Hint</summary>
  Primero debemos obtener una lista de pares de indices correspondientes a pares de paréntesis correlacionados. Para esto basta leer el string dado de izquierda a derecha y tener una lista de posiciones de abre paréntesís aún no acoplados, cada vez que encontremos un cierra paréntesis lo acoplamos con el último abre paréntesis en la lista (y lo quitamos de la lista). Usando esto sólo tenemos que ver todas las combinaciones de pares de paréntesis a eliminar, armar los strings respectivos y ordenar la lista de respuestas.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando el hint, para ver cómo generar todas las combinaciones podemos hacerlo con un for que recorra i desde 1 a (2^N - 1), donde N es la cantidad de pares de paréntesis, cada uno de estos valores para i se puede interpretar como un número binario de N bits, donde si el j-ésimo bit está prendido nos indica si eliminar el j-ésimo par de paréntesis de este caso de respuesta, los numeros binarios justo generarán todas las posibilidades en este for. Luego de armados los strings para cada i y puestas en una lista, basta ordenar y retornar.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/Zagrade.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/Zagrade.cpp">Código de ejemplo C++</a>
</details>

### H - Sum
<details> 
  <summary>Hint</summary>
  Primero debemos encontrar una base que genere el mayor largo en la suma, una base que siempre sirve para esto es el mayor dígito que nos dieron en el input + 1.
</details>
<details> 
  <summary>Solución + código</summary>
  Luego basta ir pasando la suma de estos números en la nueva base a la nueva base, podemos hacerlo todo en un while acumulando suma de digitos menores y acumulado anterior, dividiendo por la base en cada paso y dividiendo por 10 los números en cada paso (para quitar el menor dígito).
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Sum.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Sum.cpp">Código de ejemplo C++</a>
</details>

### I - Making Sequences is Fun
<details> 
  <summary>Hint</summary>
  Podemos ir agregando los números de n dígitos en bloques mientras sea posible, empezando con n = #(dígitos en m). la cantidad de números con n dígitos que se pueden agregar en un principio es (10^n - m) sumamos eso a la respuesta, updateamos m a 10^n, sumamos uno a n y repetimos mientras no nos pasemos de w.
</details>
<details> 
  <summary>Solución + código</summary>
  Cuando agregar más nos haría pasarnos de w sumamos (w - costo hasta ahora) / (n * k) (que es la máxima cantidad de números de n dígitos que nos alcanzan) y retornamos la respuesta.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MakingSequencesIsFun.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MakingSequencesIsFun.cpp">Código de ejemplo C++</a>
</details>

### J - Hyperset
<details> 
  <summary>Hint</summary>
  Podemos recorrer cada par de string en el input en  O(N^2), para cada par podemos determinar únicamente cuál sería el tercero que armaría un set con estos, por cada caracter si son iguales el tercero debe ser igual y si son distintos el tercero debe tener el que falta, luego basta chequear si el string armado estaba en el input (esto se puede hacer rápido con un set). La complejidad si es bien implementado de esta solución es de O(k * N^2 * log(N)) que pasa en el tiempo.
</details>
<details> 
  <summary>Solución + código</summary>
  Implementar el hint.
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Hyperset.py">Código de ejemplo Python</a>
  
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Hyperset.cpp">Código de ejemplo C++</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```
