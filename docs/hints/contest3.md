---
title: contest 3 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```

### D - Vanya and Lanterns 
<details> 
  <summary>Hint</summary>
  Para verificar si un radio sirve para cubrir la calle entera basta con recorrer las posiciones de forma ordenada y checkear que alcance a cubrir todos los espacios entre linternas y a los bordes.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos hacer búsqueda binaria sobre el radio óptimo, para eso podemos inicializar los límites de la búsqueda como mínimo 0 y máximo 10^9 y en cada iteración revisar si la mitad del rango alcanza a cubrir la calle, para verificar procedemos como en el hint, como en cada iteración el rango se divide a la mitad con 1000 iteraciones tendremos más que suficiente para alcanzar la precisión pedida.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/VanyaAndLanterns.cpp">Código de ejemplo</a>
</details>

### E - Need for Speed 
<details> 
  <summary>Hint</summary>
  Podemos abordar el problema como una búsqueda binaria sobre los posibles valores de la constante, piensen en cómo seria posible ocupar el tiempo real.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos como dice el hint hacer una búsqueda binaria sobre los posibles valores de la constante, para esto primero obtenemos los límites de sus posibles valores, la constante va a ser como mínimo el valor que hace a todas las entradas positivas y como máximo 2*10^6, para cada posible valor de la constante durante la búsqueda binaria obtenemos su tiempo dado como la suma de las distancias dividido en sus velocidades trasladadas.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/NeedForSpeed.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 3](../contests#contest-3) > ```{{page.title}}```
