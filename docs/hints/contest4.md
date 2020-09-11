---
title: contest 4 - hints y códigos de ejemplo
---
[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```

### A - TROY Query
<details> 
  <summary>Hint 1</summary>
  Noten que en vez de pensar en la cantidad de veces que cada fila/columna fue actualizada para llegar a la configuración actual, sólo importa la paridad de estas actualizaciones. Es decir, si fueron updateadas una cantidad par o impar de veces.
</details>
<details> 
  <summary>Hint 2</summary>
  Si una celda marca +1 entonces fue actualizada una cantidad par de veces, sólo hay 2 formas de que esto pase, que su fila y columna respectivas ambas hayan sido actualizadas una cantidad par de veces o que ambas hayan sido actualizadas una cantidad impar de veces (de esta forma la suma es par). De la misma forma, si la celda marca -1, la suma debe ser impar, por lo que una debe ser impar y la otra par. Piensen en cómo llevar registro de estas implicancias de forma que sea fácil chequear en caso de una contradicción.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos registrar las implicancias como conjuntos de un Union Find. Es decir, generamos inicialmente 2 (R + C) conjuntos, dos para cada fila y columna, que representan la posibilidad de que sean par o impar. Cuando vemos el valor de una celda unimos los conjuntos correspondientes según el hint 2, de forma que conceptualmente estamos creando conjuntos de posibles valores que si pasan deben hacerlo juntos para no contradecir los registros. Si en algún momento juntamos a una fila o columna par con su misma fila o columna impar entonces tenemos una contradicción, desde ese momento en adelante la respuesta es siempre "No".
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TROYQuery.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```
