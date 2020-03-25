---
title: contest 2 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```

### J - Hyperset

<details> 
  <summary>Hint 1</summary>
  Si fijamos dos cartas, notar que hay una única posible tercera carta que puede completar el trío de forma válida.
</details>
<details>
  <summary>Solución + código</summary>
  Iteramos sobre todos los posibles pares (for i in range(n): for j in range(i+1,n)) de cartas, y entonces calculamos la única tercera carta válida (para cada caracter, si son iguales, entonces usamos ese caracter, y si son distintos, buscamos el tercer caracter que no se ha usado). Luego chequeamos si esa carta existe (usamos un set/unordered_set para chequear esto rápido). Si la carta existe entonces sumamos 1 a un contador. Recordar dividir el contador por 3! para no incluir las permutaciones en el conteo. <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1287B_Hyperset.py">Código de ejemplo (Python)</a>, <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/Codeforces/1287B_Hyperset.cpp">Código de ejemplo (C++)</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 2](../contests#contest-2) > ```{{page.title}}```
