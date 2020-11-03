---
title: contest 8 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```

### B - Queries for Number of Palindromes
<details> 
  <summary>Hint 1</summary>
  Dado el tamaño del string podemos preprocesar todos los substrings cuadráticamente para saber cuáles conforman palíndromos, esto puede ser chequeado con Rolling Hashing hacia ambos lados por ejemplo. Piensen en cómo usar este preprocesamiento para obtener la solución.
</details>
<details> 
  <summary>Hint 2</summary>
  Dados l y r, la cantidad de substrings en [l, r] es la cantidad en [l, r - 1] más la en [l + 1, r] menos la en [l + 1, r - 1] más 1 si el mismo substring [l, r] era un palíndromo.
</details>
<details> 
  <summary>Solución + código</summary>
  Usando los hints anteriores se puede armar un algoritmo de programación dinámica que cuente los substrings que son palíndromos para cada l y r usando la recursión del hint 2.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/QueriesForNumberOfPalindromes.cpp">Código de ejemplo</a>
</details>

### C - Isomorphic Inversion
<details> 
  <summary>Hint</summary>
  Piensen en una forma greedy de seleccionar los segmentos.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos armar los segmentos de forma greedy chequenando con k de 1 creciente separando los primeros y últimos k cada vez que el sustring de los primeros k que quedan sea igual al de los últimos k. Para chequear esto se puede usar hashing preprocesado de todo el string. la respuesta será cuantas veces se pudo separar * 2 más uno si sobraron cosas al medio.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/IsomorphicInversion.cpp">Código de ejemplo</a>
</details>

### D - Efficient managing
<details> 
  <summary>Hint 1</summary>
  Primero notemos que el grafo descrito corresponde a un árbol. En ese caso podemos precalcular el precio de viajar desde un nodo raíz a cualquiera de los otros nodos en tiempo lineal con un dfs. Basta hacer un dfs que acumule el xor de las aristas usadas, pues el xor de los valores sólo tiene aquellas potencias de 2 con apariciones impares.
</details>
<details> 
  <summary>Hint 2</summary>
  Notemos que si estamos analizando el nodo i, cualquier camino desde i se puede ver como parte del subárbol de i en el arbol con la raíz original o puede ser un camino que sube y luego baja por el árbol, en ambos casos, cualquier camino que salga de i tendrá un costo igual al xor del camino precalculado desde la raíz hasta i xor con el precalculado de la raíz al nodo final del camino tomado desde i. Luego el problema puede ser reformulado a precalcular como el hint 1 y para cada i encontrar cual de los valores precalculados genera un mayor xor al ser combinados con el precalculado para i.
</details>
<details> 
  <summary>Hint 3</summary>
  Finalmente noten que cada uno de los valores precalculados puede ser cisto como un string binario, para encontrar el que genera el mayor xor con otro de estos strings, digamos x, se puede tomar un approach greedy que va condicionando tomar aquellos números con bits más grandes que difieran a los de x. Para esto piensen en qué estructura les deja ordenar los strings por los valores separando cada vez que difieren.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución corresponde a usar la reducción de los hints 1 y 2 y hacer un Trie de los strings binarios descritos en el hint 3. El Trie recibirá los valores precalculados en forma binaria pero los ingresará al Trie con los bits más grandes al principio. Esto pues podemos encontrar el mayor xor posible con los números guardados con respecto a un número x usando un approach greedy que elija bits distintos siempre que se pueda en el trie (analizando desde bits más grandes a menos igual que como fueron ingresados).
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/EfficientManaging.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 8](../contests#contest-8) > ```{{page.title}}```
