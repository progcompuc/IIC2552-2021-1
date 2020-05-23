---
title: contest 9 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 9](../contests#contest-9) > ```{{page.title}}```

### A - Merge Sort

<details> 
  <summary>Hint</summary>
  Necesitamos un arreglo que al llamar mergesort sobre él, se hagan un total de K llamadas. Pensar en una forma de simular la ejecución de mergesort distribuyendo hacia abajo las K llamadas totales que hay que hacer, y en vez de ordenar vamos poniendo valores desordenados (cosa de que al llamar el mergesort original se ejecuten esas mismas K llamadas que simulamos).
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos la misma recursión divide and conquer de mergesort(l, r, k), donde le agregamos un argumento extra k que nos dice cuantas llamadas tenemos que hacer. Si k == 1, entonces esta llamada en particular debe ser una llamada final (no más recursión hacia abajo), así que el subarreglo correspondiente debe estar ordenado (llenamos con valores crecientes). Si k > 1, entonces hay que decidir cómo repartir (k-1) llamadas entre las dos llamadas hijas. Pueden haber varias opciones. Una opción posible es tirar la mayor cantidad de llamadas a la izquierda y lo que sobre a la derecha. Como sea que distribuyamos, nos van a quedar los dos subarreglos hijos con valores asignados. Para garantizar que la unión de los dos subarreglos quede desordenada, le podemos sumar un offset a los valores del subarreglo hijo izquierdo para garantizar que todos esos valores sean mayores estrictos a los valores del subarreglo derecho (con eso queda sí o sí desordenado). Los casos bordes en que se retorna -1 son cuando el k supera el máximo de llamadas posibles o bien cuando k es par. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/873D_MergeSort.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 9](../contests#contest-9) > ```{{page.title}}```
