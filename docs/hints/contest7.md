---
title: contest 6 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```

### A - Staircases
<details>
  <summary>Hint</summary>
  Un posible DP podría ser de la forma DP(n, h) = todas las formas de construir escaleras de n bloques tal que el primer peldaño es de altura h (pero si se te ocurre otro DP, go ahead)
</details>
<details> 
<summary>Solución + código</summary>
La recurrencia del DP(n, h) del hint, ignorando casos bases, sería la sumatoria sobre x = h+1 ... n-h de DP(n-h, x). <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Otros/Staircases.cpp">Código de ejemplo</a>
</details>

### B - The Coin Change Problem
<details>
  <summary>Hint</summary>
  Pensar en un DP de la forma DP(k, i) = todas las formas que podemos generar el monto 'k' usando monedas de tipo i, i+1, ..., m-1. La llamada inicial del DP sería DP(n, 0), ya que queremos contar todas las formas de generar el monto 'n' teniendo a nuestra disposición todas las monedas (del 0 al m-1). Para deducir la recurrencia del DP, pensar que tenemos 2 opciones: usar la moneda i-ésima o no usarla, si la usamos después podemos usarla de nuevo, y si no la usamos entonces nos pasamos a la siguiente moneda.
</details>
<details> 
<summary>Solución + código</summary>
 Implementar el DP(k,i) explicado conceptualmente en el hint. Si usamos la moneda i, nos queda el subproblema DP(k - value[i], i), si no la usamos, nos queda el subproblema DP(k, i+1). <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/HackerRank/TheCoinChangeProblem.cpp">Código de ejemplo</a>
</details>

### C - Baby Ehab Partitions Again
<details>
  <summary>Hint</summary>
  Notemos que la suma debe ser par para poder separar en estos 2 grupos. Además, si no es posible separar en 2 grupos como los que se piden entonces la respuesta debe ser 0.
  Para saber si es posible encontrar esta separación podemos aplicar programación dinámica, piensen en un dp parecido al del problema B.
</details>
<details> 
<summary>Solución + código</summary>
  Usando el hint, para saber si existe respuesta basta una función de programación dinámica que vea si es posible elegir valores en el arreglo tal que su suma sea la mitad de la suma total (usando una función DP(i, v) donde i es el valor en el que vamos y v es la suma que nos falta, la respuesta será saber si es posible DP(0, S/2) con S suma total). En caso de si haber forma, notemos que basta quitar un número impar, en caso de no haberlo dividimos todos por dos hasta que haya y lo quitamos.
<a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/BabyEhabPartitionsAgain.cpp">Código de ejemplo</a>
</details>

### D - Greenhouse Effect
<details> 
  <summary>Hint 1</summary>
  Un primer insight es darse cuenta de que al poder colocar las plantas en el lugar que queramos, las coordenadas de estas no son realmente importantes para el problema, sólo el orden inicial de los tipos.
</details>
<details> 
  <summary>Hint 2</summary>
  Podemos descomponer el problema en subproblemas que deciden para cada planta si es óptimo moverla o no, y retornar la opción que desencadene menos movimentos al largo plazo.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución de este problema es similar a la del problema G. Podemos hacer un dp que dependa de 2 cosas, indice de la planta que decidiremos ahora y el mayor de los tipos de planta que hemos no movido (en cuanto a su tipo, no coordenadas). Recorremos los problemas de izquierda a derecha, decidiendo para cada planta en el dp, de esta forma el óptimo para un subproblema depende de los óptimos de los subproblemas siguientes. Nos importa el mayor de los tipos que no hemos movido en las plantas que ya decidimos, pues si este tipo es mayor que el de la planta que decidimos ahora, no podemos no moverla pues no generaría una configuración deseada.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/GreenhouseEffect.cpp">Código de ejemplo</a>
</details>

### E - Looking for Order
<details>
  <summary>Hint</summary>
  Podemos representar los objetos que tenemos que recoger con los bits de un entero 'mask'. Entonces podemos pensar en un DP de la forma DP(mask) = el mínimo tiempo para recoger los objetos indicados por los bits prendidos de 'mask', y la solución al problema inicial sería DP(2^N-1), con N siendo la cantidad de objetos.
</details>
<details> 
<summary>Solución + código</summary>
Implementamos el DP(mask) definido conceptualmente en el hint. Internamente, dentro de DP(mask) tenemos que tomar la decisión de cómo ir a buscar el primer objeto con bit prendido. Tenemos dos opciones: 1) ir a buscarlo y traerlo de vuelta a la mochila altiro o 2) ir a buscarlo, luego aprovechar de ir a buscar un segundo objeto (con bit prendido también) y luego traernos los dos objetos juntos. En cada caso nos quedaría un submask de mask como subproblema a resolver (llamamos a DP(submask) para resolver el subproblema). <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/LookingForOrder.cpp">Código de ejemplo</a>
</details>

### F - Mixtures
<details> 
  <summary>Hint</summary>
  Podemos ver el problema desde el final del proceso hasta el principio, es decir, cual es el óptimo para las últimas 2 pociones que mezclemos? Sabemos que el humo que genera esta última mezcla sólo depende de los colores de las mezclas que contiene cada una, pero al poder juntarse sólo con adyacentes, necesariamente cada mezcla es la unión de un segmento contiguo de las pociones iniciales. Si pensamos el proceso de esta forma basta con tomar cada vez la opción que nos genere menos humo en generar estas "últimas pociones" y mezclarlas.
</details>
<details> 
  <summary>Solución + código</summary>
  Siguiendo lo expresado en el Hint, podemos hacer un DP sobre todos los segmentos contiguos de pociones iniciales, y para cada uno de estos el dp calcula el punto óptimo para unirlo, es decir cómo separar en 2 el segmento en cuestión de tal forma que si cada uno de los nuevos segmentos se mezcla de manera óptima, esta última mezcla genere la menor cantidad de humo (tomando en cuenta el humo óptimo de sus subsegmentos). Para calcular el humo de los subsegmentos basta ocupar la misma función dp sobre ellos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/Mixtures.cpp">Código de ejemplo</a>
</details>

### G - Scuba diver
<details> 
  <summary>Hint</summary>
  Podemos pensar este problema como decidir cilindro por cilindro si es que es óptimo tenerlo en los tanques finales o no, de esta forma se puede pensar la decisión de cada cilindro como subproblema, donde esta depende del peso óptimo para tener el oxígeno y nitrógeno restante (suponiendo que tomaste el tanque).
</details>
<details> 
  <summary>Solución + código</summary>
  Tomando en cuenta el hint, podemos pensar en hacer las elecciones en orden, es decir, podemos hacer un dp que dependa de 3 variables, indice, oxígeno a llevar y nitrógeno a llevar, y el índice indica que decidiremos sobre el i-ésimo tanque considerando sólo los tanques con índices mayores o iguales a i. Esto no cambia el resultado, pues cualquier configuración de tanques puede ser elegida en orden. Luego para cada subproblema hay dos opciones, llevar o no el i-ésimo tanque, si no lo llevamos el subproblema es equivalente al dp desde i+1 con los mismos requerimientos de oxígeno y nitrógeno. Pero si lo llevamos la respuesta es el peso del tanque más el óptimo desde i+1 de los requerimientos quitándole el aporte del tanque i.
  De esta forma la respuesta puede ser accedida desde el subproblema desde el primer índice y los requerimientos iniciales.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/ScubaDiver.cpp">Código de ejemplo</a>
</details>

### H - Changing A String
<details> 
  <summary>Hint</summary>
  Podemos pensar el problema como ir igualando los strings de a poco de izquierda a derecha, de esta forma podemos definir un subproblema del dp como minimizar la cantidad de movimientos dado que estoy en el el índice i del primer string y en el índice j del segundo (asumes que ya igualaste lo anterior).
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos lo que dice el Hint. Para cada subproblema el mínimo es el que genere menos pasos de todas las opciones que tengan sentido, entre insertar, reemplazar, borrar o avanzar, que desencadenan a su vez una cantidad de movimientos que dependen de los siguientes subproblemas. Finalmente para recuperar los pasos de una estrategia óptima basta ir recorriendo las decisiones óptimas usando los valores que quedaron guardados en el memo. Es recomendable usar una funcion recursiva similar a la del dp para este último paso.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/ChangingAString.cpp">Código de ejemplo</a>
</details>

### I - Rotate Columns (Hard Version)
<details> 
  <summary>Hint 1</summary>
  Si M > N, notar que podemos ordenar las columnas de mayor a menor de acuerdo al máximo valor por columna, quedarnos con las primeras N columnas y descartar el resto. Esto porque cualquier solución que no use alguna(s) de las primeras N columnas siempre la podemos empatar o mejorar rotando apropiadamente las primeras N columnas.
</details>
<details> 
  <summary>Hint 2</summary>
  Notar que dada una configuración cualquiera de columnas rotadas, podemos pensar que cada columna contribuye con 0 o más "máximos" a la sumatoria de máximos. Por ejemplo, la primera columna contribuye con máximos en las filas 1 y 3, la segunda columna contribuye con máximos en las filos 2 y 5, la tercera columna contribuye con un máximo en la fila 4, etc. En otras palabras, si nosotros exploramos exhaustivamente el "árbol de posibles contribuciones de máximos por columna" (pesándolo como el árbol de decisiones de un backtracking), la solución óptima va a corresponder a una rama de ese árbol. La forma de explorar sería con una función search(i, mask) = la mayor suma de máximos que podemos armar con las columnas i, i+1, i+2, ..., min(N,M)-1 suponiendo que las filas indicadas por los bits prendidos de 'mask' están desocupadas (las otras filas ya tienen máximos asignados). El search partiría con search(0, 2^N-1).
</details>
<details> 
  <summary>Hint 3</summary>
  Supongamos que para la columna i-ésima, yo escojo que dicha columna va a contribuir con máximos en las filas 1 y 3. Dado que yo puedo rotar la columna como yo quiera, esto es equivalente a haber fijado las filas 2 y 4, o haber fijado las filas 3 y 5, etc. Es decir, hay muchos subconjuntos de filas que son equivalentes bajo rotación, es decir, que forman una clase de equivalencia. Entonces uno puede hacer dos cosas: 1) precomputar estas clases de equivalencia y 2) precomputar la rotación óptima (que maximiza la suma) para cada clase de equivalencia.
</details>
<details> 
  <summary>Solución + código</summary>
  Primero nos quedamos con min(M,N) columnas según el Hint 1. Luego buscamos la suma de máximos óptima con un DP(i, mask) como se indicó en el Hint 2. Internamente, para la i-ésima columna debemos escoger un 'submask' de 'mask' (subconjunto de las filas disponibles) donde esta columna contribuirá con máximos. Dado un 'submask', podemos buscar la clase de equivalencia de 'submask' (que podemos precomputar de antes) y luego la suma de la rotación óptima de la columna i-ésima para dicha clase de equivalencia (también precomputable de antes). Entonces escoger un 'submask' de 'mask' para la columna i tiene un costo asociado de maxsum[i][mask2class[submask]] + DP(i+1, mask - submask). Es súper importante hacer estos pre-cómputos porque de no hacerlos, estaríamos obligados a hacerlos a cada rato dentro del DP y esto daría TLE por los límites del problema y la restricción de tiempo (este es un excelente problema para aprender el valor de precomputar muchas cosas). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1209E2_RotateColumns(HardVersion).cpp">Código de ejemplo</a>
</details>

### J - Knapsack for all Segments
<details>
  <summary>Hint</summary>
  Notar que el problema es equivalente a contar todas las tuplas (L, sequence, R), donde sequence = (i1, i2, ..., ik) es una secuencia de índices de algún largo k tal que L <= i1 < i2 < .. < ik <= R y A[i1] + A[i2] + ... + A[ik] = S. Usando nuestro conocimiento previo de backtracking, todos las tuplas (L, sequence, R) válidas las podemos contar explorando un árbol de decisiones sobre los índices 0, 1, ..., N-1, donde por cáda índice vamos decidiendo si lo consideramos el L de la tupla, algún elemento de sequence o el R de la tupla (en ese orden). Pero bactracking daría TLE. La gracia está en darse cuenta que hay subproblemas que se repiten, y ahí podemos aplicar DP.
</details>
<details> 
<summary>Solución + código</summary>
Hacemos un DP(i, c, flag) = todas las formas de completar tuplas (L, sequence, R) válidas, suponiendo que estamos tomando decisiones a partir del índice i hacia la derecha (i, i+1, ..., N-1), debemos terminar de escoger elementos tal que su suma sea 'c', y si flag es 0 todavía estamos en la fase de escoger el índice que va a ser el 'L' de la tupla, en cambio si flag es 1 significa que ya escogimos el 'L' y ahora tenemos que completar el sequence y luego escoger el índice de 'R'. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/AtCoder/abc159_f_KnapsackForAllSegments.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```
