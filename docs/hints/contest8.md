---
title: contest 8 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```

### A - Letters Cyclic Shift
<details> 
  <summary>Hint</summary>
  Siempre conviene achicar las letras más a la izquierda posible (esto es lo greedy).
</details>
<details> 
  <summary>Solución + código</summary>
  Encontramos la primera letra que no es 'a' de izquierda a derecha, luego desde ahí encontramos la última letra que no es 'a', entonces todo ese segmento lo cyclic-shifteamos. Si no logramos encontrar ningún segmento así, quiere decir que el string tiene puras a's, pero como estamos obligados a cyclic-shiftear por lo menos un caracter, entonces la última 'a' la convertimos en 'z'. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/709C_LetterCyclicShift.cpp">Código de ejemplo</a>
</details>

### B - Black and White Stones
<details> 
  <summary>Hint 1</summary>
  Si hay K letras B, podemos visualizar una línea vertical divisoria entre los índices K-1 y K. Todas las letras B que están a la derecha de la línea divisoria hay que trasladarlas o teletransportarlas a las posiciones con W que están a la izquierda de la línea divisoria.
</details>
<details> 
  <summary>Hint 2</summary>
  Notar que trasladar uno a uno es mejor que teletransportar hasta que la distancia se vuelve muy grande, en cuyo caso teletransportar comienza a ser mejor.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos una solución greedy en la que buscamos llenar cada posición W a la izquierda de la línea divisoria (hint 1) con los B a la derecha de la línea divisoria. Usamos dos punteros, un puntero de derecha a izquierda para los W y otro puntero de izquierda a derecha para los B. El primero parte en el índice K-1 y el segundo en el índice K (donde K es la cantidad de letras B que hay en total). Para cada par de W y B que encontramos, usamos la opción más barata entre teletransportar y trasladar uno a uno. Sumamos todo eso y esa es la respuesta. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/LiveArchive/6822_BlackAndWhiteStones.cpp">Código de ejemplo</a>
</details>

### C - Bridge Crossing
<details> 
  <summary>Hint</summary>
  Pensar en una solución por rondas, donde cada ronda comienza con el bote a la izquierda y el objetivo de la ronda es enviar a las 2 personas más lentas a la orilla derecha de la forma más eficiente posible.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacer una solución por rondas como lo indica el hint. Hay dos formas de enviar a las dos personas más lentas: 1) enviamos cada persona más lenta acompañada por la persona más rápida y nos devolvemos con la persona más rápida; 2) enviamos las dos personas más rápidas, nos devolvemos con la más rápida, luego enviamos las personas más lentas juntas y finalmente nos devolvemos con la segunda más rápida que dejamos al otro lado. De esas dos opciones escogemos la que sea mejor. Tener cuidado con que en la última ronda no hay que volver a la orilla izquierda (o si no no sería la última ronda). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codechef/GEEK04_BridgeCrossing_v2.cpp">Código de ejemplo</a>
</details>

### D - TheQueue
<details> 
  <summary>Hint 1</summary>
  Si destacamos en una recta de tiempo los intervalos en que la recepcionista está ocupada, para esperar 0 tendríamos que llegar en un instante pertenciente a un gap entre 'ts' y el primer intervalo, un gap entre 2 intervalos, o un gap entre el último intervalo y 'tf'. Es decir, para todos los gaps excepto el último siempre hay alguien que llega después, así que podemos cubrir todos esos casos preguntándonos qué pasa si llegamos en t_i-1 para cada persona i. Para el gap entre el último intervalo y 'tf', nos basta con probar en (tf - tiempo_atención).
</details>
<details> 
  <summary>Hint 2</summary>
  Si no podemos ser primeros en la cola al llegar (i.e. esperar 0), entonces estamos obligados a llegar y que haya gente en la cola antes que nosotros. Entonces tenemos que decidir en qué posición de la cola quedaremos cuando llegemos. Esto es equivalente a decidir justo antes de quién voy a quedar parado. Si quiero quedar justo antes que la persona i-ésima en la cola, lo greedy es llegar justo en el instante t_i - 1.
</details>
<details> 
  <summary>Solución + código</summary>
  El problema se puede resolver simulando la evolución de la cola en el tiempo e inyectando en la simulación consultas del tipo "cuánto tendría que esperar para que me antiendan si justo llego en el instante t". La simulación la podemos hacer con eventos con timestamps. Un evento puede ser del tipo "recepcionista llega", "recepcionista se va", "llega persona", "se va persona" y "consulta". Por cada persona i-ésima agregamos un evento tipo "consulta" con tiempo (t_i - 1) (siempre que t_i - 1 >= 0), y agregamos también un evento consulta con tiempo (t_f - tiempo_atención). Simulamos eventos y cuando nos toque un evento consulta, la espera será (tiempo_atención * personas_en_cola + tiempo que le falta a la recepcionista para desocuparse). Si la recepcionista me alcanza a atender dada esa espera, actualizo mi respuesta, e imprimo la mejor respuesta luego de simular todo. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/767B_TheQueue.cpp">Código de ejemplo</a>
</details>

### E - Criss-Cross Cables
<details> 
  <summary>Hint</summary>
  Si ordenamos los cables de menor a mayor y las distancias entre pares de puertos de menor a mayor, entonces es fácil hacer una solución con dos punteros. El problema es que la cantidad de pares de puertos es cuadrática y por ende demasiado grande (TLE). Piensa en una forma de ir recorriéndolos en orden sin tener que generarlos todos.
</details>
<details> 
  <summary>Solución + código</summary>
  Usamos una priority_queue para ordenar pares de puertos. Inicialmente la llenamos con los pares consecutivos (i, i+1). Cuando sacamos el par (i, j), metemos el par (i, j+1). Al mismo tiempo tenemos un puntero en nuestros cables. Si en algún punto un cable no se la puede con el par (i, j) actual, menos se la va a poder con los pares futuros, así que inmediatamente no se puede. Si se nos acaban los cables y siempre pudimos, sí se puede. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/kattis/crisscrosscables.cpp">Código de ejemplo</a>
</details>

### F - DZY Loves Modification
<details> 
  <summary>Hint 1</summary>
  Si el problema fuera sólo tomar columnas o sólo tomar filas, podemos tomar un approach greedy tomando siempre la que me genere mayor ganancia (tomando en cuenta la disminución de la elegida luego de cada elección). En este caso sin embargo la combinación puede afectar el resultado.
</details>
<details> 
  <summary>Hint 2</summary>
  Supongamos que queremos tomar i filas y (k - i) columnas, podemos elegir las filas y columnas que tomaremos usando el Hint 1, para calcular la ganancia general que esto nos genera hay que considerar además la disminución que genera sobre las columnas el elegir una fila y viceversa.
</details>
<details> 
  <summary>Hint 3</summary>
  Siguiendo con el hint anterior notemos que esta ganancia de elegir i filas y (k - i) columnas, no depende del orden en que sean elegidas (respecto a elegir primero filas o columnas o combinadas). La ganancia siempre será R(i) + C(k - i) - i * (k - i) * P. Donde R(i) es la ganancia de elegir i filas de forma consecutiva y C(i) lo mismo sobre columnas.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos precalcular los valores de R(i) y C(i) descritos en el Hint 2 para i de 0 a k y luego la respuesta será el máximo de R(i) + C(k - i) entre todos los i de 1 a k.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/DZYLovesModification.cpp">Código de ejemplo</a>
</details>

### G - Nested Dolls
<details> 
  <summary>Hint 1</summary>
  Busque una forma de ordenar las muñecas tal que el problema sea más fácil.
</details>
<details> 
  <summary>Hint 2</summary>
  Ordene de mayor a menor (>) en ancho y desempate de menor a mayor (<) en altura. Vuelva a pensar el problema considerando este orden.
</details>
<details> 
  <summary>Solución + código</summary>
  Si consideramos el orden descrito en los hints, podemos ir recorriendo las muñecas una por una (en el orden descrito) y elegir cual de las muñecas que ya hemos visto podemos juntar a esta (encerrar con la que estamos viendo). Como las muñecas están ordenadas crecientemente en ancho, todas las muñecas que ya hemos visto tienen ancho no mayor a la actual. Luego para poder ser elegida sólo importa la altura. Si mantenemos las muñecas que ya vimos ordenadas por altura, por ejemplo en un multiset, podemos encontrar rápidamente la con la altura más alta que puedo encerrar, si junto la actual con esta muñeca encontrada (sacando la encontrada del multiset e ingresando la nueva) siempre tendré en el multiset a las muñecas más comprimidas posibles. La respuesta final será el tamaño final del multiset.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/NestedDolls.cpp">Código de ejemplo</a>
</details>
  
### H - Crazy Driver
<details> 
  <summary>Hint</summary>
  Notemos que vamos a tener que ir y volver entre algunos pares de puertas mientras esperamos a que la siguiente sea abierta. Una forma de hacer este problema de forma greedy elegir este par de puertas en las que daré vueltas como las que tengan el camino asociado más barato.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos pensar el problema como elecciones consecutivas, vamos puerta por puerta viendo si es que el tiempo que llevamos es suficiente, si no lo es vamos agregando de a 2 al tiempo y sumando al costo 2 veces el costo menor visto hasta que nuestro tiempo sea suficiente. La respuesta será el costo acumulado total.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/CrazyDriver.cpp">Código de ejemplo</a>
</details>

### I - Change-free
<details> 
  <summary>Hint 1</summary>   
  Notemos que nos podemos olvidar de los billetes a pagar y sólo pensar en las monedas disponibles. Sólo hay 2 formas de pagar que podrían llegar a ser óptimas cada día, pagar C[i]/100 billetes y C[i]%100 monedas (change free) o pagar (C[i]/100 + 1) billetes y 0 monedas. Ninguna otra forma de pagar nos da beneficios o es óptima.
</details>
<details>
  <summary>Hint 2</summary>
  Notemos que la ganancia en monedas que nos genera el pagar de la segunda forma respecto a pagar de la primera siempre es de exactamente 100 monedas (pues no pagamos C[i]%100 y recibimos 100 - C[i]%100).
</details>
<details> 
  <summary>Solución + código</summary>
  Notemos que para poder pagar justo un día necesitamos tener la cantidad de monedas necesarias, si las tenemos lo óptimo es pagarlas, de otro modo podemos elejir de forma greedy si parar de la segunda forma o elegir un día de los anteriores donde hayamos pagado justo y pasarlo a la segunda forma para pagar justo ahora. Para hacer esta elección basta con hacer uso de alguna estructura que nos ordene lo que hayamos visto, por ejemplo una priority_queue en c++.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/ChangeFree.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```
