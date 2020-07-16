---
title: contest 13 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 13](../contests#contest-13) > ```{{page.title}}```

### A - Environment Protection
<details> 
  <summary>Búsqueda binaria sirve</summary>
</details>
<details> 
  <summary>Solución + código</summary>
  Hacer búsqueda binaria, y en el predicado hacer integración numérica. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/LiveArchive/6135_EnvironmentProtection.cpp">Código de ejemplo</a>
</details>

### B - Billiard
<details> 
  <summary>Hint 1</summary>
  En primer lugar, si la dirección es paralela a algún eje la respuesta se puede obtener chequeando las coordenadas directamente. Notemos que en el resto de los casos podemos considerar que la dirección de la bola siempre será de 45 grados subiendo, de lo contrario podemos rotar la tabla para que sea así.
</details>
<details> 
  <summary>Hint 2</summary>
  Imaginemos, en vez de una bola rebotando, que tenemos una teselación infinita del plano con tablas de N x M. De esta forma un lanzamiento de la bola se puede ver como una recta en esta teselación y si en su camino hay un punto de la forma (k1 * N, k2 * M) entonces cae en un agujero de la tabla.
  
  Usando el hint 1 asumimos que la bola sólo sube en 45 grados. Denominemos rx como la distancia de la coordenada x inicial a N, y ry a la distancia en el eje y a M. Cualquier punto en la recta que transita la bola será de la forma (x, y) + (d, d). Luego para llegar a un punto de la forma (k1 * N, k2 * M) se necesita que exista d tal que d = rx (mod N) y, d = ry (mod M), de lo contrario será imposible que x + d = 0 (mod N) y, x + d = 0 (mod M) al mismo tiempo.
</details>
<details> 
  <summary>Solución + código</summary>
  Para encontrar un d como descrito en el hint 2 basta usar CRT para las ecuaciones d = rx (mod N) y, d = ry (mod M). Si ha solución entonces podemos obtener las constantes k1 y k2 de (k1 * N, k2 * M) como (d - rx) / N y (d - ry) / M respectivamente. Luego obtenemos el agujero en que cae con argumentos de rotación y paridad.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/Billiard.cpp">Código antiguo del ayudante (cuando usaba templates)</a>
</details>

### C - Spaceology vs. Chronistics
<details> 
  <summary>Hint 1</summary>  
  Notemos que eventualmente ambos scientíficos se moverán en ciclos, podemos simular una cantidad de pasos para asegurarnos que entren al ciclo y seguir analizando desde ahí. Para asegurar un ciclo basta simular N pasos, pueden poner más para estar seguros.
</details>
<details> 
  <summary>Hint 2</summary>
  Si no han chocado en los primeros N pasos simulados podemos chequear los ciclos en que se mueven ambos científicos. Para cada uno podemos calcular fácilmente el largo del ciclo y en cuantos pasos llegan a cada intersección en sus ciclos. Si hay una intersección por la que ambos científicos pasen durante sus ciclos podemos chquear si alguna vez estarán ahí al mismo tiempo haciendo uso de CRT para las ecuaciones t = t1 (mod l1), t = t2 (mod l2) donde t1 y t2 son los tiempos en que cada ciclo se demora en llegar a ese punto y l1, l2 son los largos de los ciclos.
</details>
<details> 
  <summary>Solución + código</summary>
  Basta hacer lo indicado en el hint 2 para cada intersección a la que ambos científicos puedan llegar y acumular el menor de los tiempos obtenidos. Si nunca estaban ambos al mismo tiempo devolvemos -1.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Timus/SpaceologyVsChronistics.cpp">Código de ejemplo</a>
</details>

### D - Santa's Bot
<details> 
  <summary>Hint</summary>
  Podemos obtener el inverso modular de un número simplemente usando el algoritmo de euclides extendido en (x, M) donde x es el número a invertir y M es el módulo. Luego basta contar casos favorables y casos totales para concluir.
</details>
<details> 
  <summary>Solución + código</summary>
  Para cada combinación (x, y) la probabilidad de que elegir z sea exitoso es C[y] / N donde C cuenta cuantas personas pidieron el regalo y. Además la cantidad de formas de elegir (x, y) es 1 / (N * K[x]) donde K[x] cuenta cuantas cosas pidió x. Luego basta ir sumando probabilidades del estilo C[y] / (N * N * K[x]) para cada combinación de x, y. Podemos sumar pues estamos en espacio modular (Z_MOD).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/SantasBot.cpp">Código de ejemplo</a>
</details>

### E - Chinese Remainder Theorem (non-relatively prime moduli)
<details> 
  <summary>Hint</summary>
  Problema hello world de CRT
</details>
<details> 
  <summary>Solución + código</summary>
  CRT, revisar materia del curso. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/kattis/generalchineseremainder.cpp">Código de ejemplo</a>
</details>

### F - Whipe Your Whiteboards
<details>
  <summary>Hint</summary>
  El algoritmo de extendido de Euclides es útil
</details>
<details> 
  <summary>Solución + código</summary>
  Básicamente queremos encontrar a y b tales que a * r + b * s = q. Podemos usar euclides extendido para encontrar x e y tales que x * r + y * s = gcd(r,s) = g. Luego si g divide a q, todos los a's y b's que sirven están dados por a(k) = x * q/g + k * s/g  y b(k) = y * q/g - k * r/g, donde k es cualquier número entero. Como necesitamos que a(k) > 0 y b(k) > 0, si despejamos k en ambas inecuaciones y tenemos cuidado con el efecto del signo de las cosas en la desigualdad, notaremos que el k más chico que sirve es el mínimo entre dos opciones (o quizá uno más que eso). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/kattis/wipeyourwhiteboards.cpp">Código de ejemplo</a>
</details>

### G - Prime Reduction
<details>
  <summary>Hint</summary>
  Para este probema la clave es poder simular el proceso de forma rápida.
</details>
<details> 
  <summary>Solución + código</summary>
  Para simularlo rápidamente sólo necesitamos un algoritmo capaz de calcular la descomposición prima de un número en un tiempo no muy grande. Esto se puede implementar fácilmente en O(sqrt(N) + log(N)) iterando sobre todos los números desde 2 hasta sqrt(n) y si el número divide a N entonces es un divisor primo, (debemos dividir N por el número encontrado lo más que se pueda para que el razonamiento siga siento válido).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/PrimeReduction.cpp">Código de ejemplo</a>
</details>

### H - Higgs Bosson
<details>
  <summary>Hint</summary>
  Hay que ponerse en varios casos, y en cada caso implementar la matemática bien.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución es básicamente el hint pero hecho con mucho cuidado. Primero hay que ver dos casos generales: 1) qué pasa cuando las ecuaciones de los radios son iguales (a1 == a2 y b1 == b2) y 2) qué pasa cuando no. En el primer caso el radio siempre es el mismo, entonces sólo importa el ángulo (excepto cuando el radio se hace 0, y ahí el ángulo no importa). En el segundo caso hay que ver el caso en que r1(t) y r2(t) se intersectan en un solo punto, cuando r1(t) == -r2(t) para todo t y cuando r1(t) y -r2(t) se intersectan en un solo punto. En cada caso hay que manejar qué condiciones tienen que cumplirse para el radio. La respuesta final es el mínimo t >= 0 encontrado entre todos los casos y subcasos. En el <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/SAMER08H_HiggsBoson.cpp">código de ejemplo</a> tengo comentados los casos y subcasos.
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 13](../contests#contest-13) > ```{{page.title}}```
