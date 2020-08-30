---
title: contest 2 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```

### A - Petya and Exam
<details> 
  <summary>Hint</summary>
  Los eventos interesantes son los momentos en que las preguntas se convierten en obligatorias. Diseña un algoritmo que se ponga en todos esos momentos interesantes.
</details>
<details> 
  <summary>Solución + código</summary>
  Ordenamos las preguntas por su tiempo en que se vuelven obligatorias. Iteramos sobre las preguntas y mantenemos contadores sobre la cantidad de preguntas obligatorias easy y hard que hay que hacer. Sea t el instante en que un grupo de preguntas se vuelven obligatorias. Un momento interesante es t-1 (uno antes que se vuelvan obligatorias), en dicho instante se maximiza el tiempo disponible para resolver las preguntas obligatorias que vienen antes. Si en t-1 alcanzamos a hacer todas las obligatorias, el tiempo sobrante lo gastamos codiciosamente en las preguntas fáciles y el resto en las difíciles que sobran. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1282C_PetyaAndExam.cpp">Código de ejemplo</a>
</details>

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

### C - The Queue
<details> 
  <summary>Hint 1</summary>
  Por simplicidad, notar que podemos ignorar toda la gente que llega un tiempo >= tf.
</details>
<details> 
  <summary>Hint 2</summary>
  Si hubiese algún instante en que pudiesemos llegar y esperar 0, significa que hay una ventana de tiempo entre ts y tf de ancho >= 1 durante la cual la recepcionista está desocupada. Esa ventana tiene cota por la derecha ya sea el instante de llegada de alguien, o bien tf. Podemos cubrir todos esos casos considerando cada instante que llega alguien menos 1, o bien el instante en que se va la última persona (ignorando los que llegan >= tf).
</details>
<details> 
  <summary>Hint 3</summary>
  Si no fuese posible esperar 0, en cualquier instante que lleguemos siempre quedaremos ubicados atrás de alguien en la cola. Podemos ponernos en todos esos casos suponiendo que llegamos en cada instante que llega alguien menos 1 (el menos 1 es para minimizar la espera).
</details>
<details> 
  <summary>Solución + código</summary>
  Según lo explicado en los hints, básicamente los únicos instantes interesantes son los tiempos de llegadas menos 1 de cada persona que llega en un t <= tf, o bien el instante en que se desocupa la última persona. Hacemos una simulación de la cola con una queue y la secuencia de instantes de llegada de la gente. Antes de procesar el instante t, sacamos de la cola todos los que se van antes de t (hasta t-1). Ahí vemos qué pasaría si llegamos justo en t-1 y actualizamos la respuesta. Lo mismo para el instante en que se va la última persona. Un caso borde es que nadie llegue <= tf. En ese caso es obvio que la espera es 0 (basta llegar en ts y estamos). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/767B_TheQueue.cpp">Código de ejemplo</a>
</details>

### D - Powerful Array
<details> 
  <summary>Hint</summary>
  Ordenar las queries de forma muy inteligente puede servir.
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="https://cp-algorithms.com/data_structures/sqrt_decomposition.html#toc-tgt-4"> El algoritmo de MO</a>. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/86D_PowerfulArray.cpp">Código de ejemplo</a>
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

### F - Greg and Array
<details> 
  <summary>Hint</summary>
  Podemos registrar la cantidad de veces que se termina haciendo cada update usando un arreglo de diferencias, la idea es la siguiente, usamos un arreglo U que empieza con 0's y si queremos hacer los updates entre x e y hacemos U[x] += 1, U[y + 1] += 1, luego despues de todas las queries podemos recorrer el arreglo U y la suma de los valores nos entrega la cantidad de veces que se hace cada update.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos usar la idea del hint 2 veces, una vez para cuantas veces se hace cada update y otra para saber cuanto se le suma a los A[i], en el caso de la segunda se puede tener un arreglo C donde para cada update hacemos C[L[i]] += d[i] * s, C[R[i] + 1] -= d[i] * s, donde L[i], R[i], d[i] son los límites del update i, y s es la variable acumulada del arreglo U. Finalmente la respuesta final se obptiene recorriendo C. La complejidad final de esta solución termina siendo lineal en N y M.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/GregAndArray.cpp">Código de ejemplo</a>
</details>

### G - They Are Everywhere
<details> 
  <summary>Hint</summary>
  Piensen en cómo calcular rápidamente cual es el menor índice j necesario a visitar asumiendo que empiezo a visitar desde i. Esto se hará para cada indice inicial.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos usar arreglos acumulados de aparición de cada letra, como son letras minúsculas y mayúsculas necesitaremos a lo más 54 arreglos. Luego para cada índice de inicio i, podemos encontrar el menor índice necesario j a partir de una búsqueda binaria, sólo se necesita chequear que cada letra ocurra al menos una vez en el rango. La complejidad final es en el peor caso O(54 * N * log N), lo que pasa en tiempo.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TheyAreEverywhere.cpp">Código de ejemplo</a>
</details>

### H - Rotation Matching
<details> 
  <summary>Hint 1</summary>
  Notar que el problema se simplifica si asumimos que una permutación es fija, la otra se gira y sólo se puede girar hacia la derecha.
</details>
<details> 
  <summary>Hint 2</summary>
  Si queremos que dos números queden matcheados, existe un único giro válido hacia la derecha de la permutación girable para dejarlos matcheados.
</details>
<details> 
  <summary>Solución + código</summary>
  Iteramos de 1 a N y calculamos el giro único que deja el par de valores matcheados. El giro que maximiza la cantidad de matches es el óptimo. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1365C_RotationMatching.cpp">Código de ejemplo</a>
</details>


<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```
