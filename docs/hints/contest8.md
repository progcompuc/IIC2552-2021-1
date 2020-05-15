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

### C - Bridge Crossing
<details> 
  <summary>Hint</summary>
  Pensar en una solución por rondas, donde cada ronda comienza con el bote a la izquierda y el objetivo de la ronda es enviar a las 2 personas más lentas a la orilla derecha de la forma más eficiente posible.
</details>
<details> 
  <summary>Solución + código</summary>
  Hacer una solución por rondas como lo indica el hint. Hay dos formas de enviar a las dos personas más lentas: 1) enviamos cada persona más lenta acompañada por la persona más rápida y nos devolvemos con la persona más rápida; 2) enviamos las dos personas más rápidas, nos devolvemos con la más rápida, luego enviamos las personas más lentas juntas y finalmente nos devolvemos con la segunda más rápida que dejamos al otro lado. De esas dos opciones escogemos la que sea mejor. Tener cuidado con que en la última ronda no hay que volver a la orilla izquierda (o si no no sería la última ronda). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codechef/GEEK04_BridgeCrossing.cpp">Código de ejemplo</a>
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

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```
