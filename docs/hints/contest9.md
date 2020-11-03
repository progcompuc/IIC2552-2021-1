---
title: contest 9 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 9](../contests#contest-9) > ```{{page.title}}```

### A - Gluing Pictures
<details> 
  <summary>Hint 1</summary>
  Noten que basta usar un approach greedy donde vamos completando la palabra buscado usar substrings lo más grandes posibles del string grande. Esto siempre será óptimo, sólo queda saber cómo buscar el mayor substring que podemos tomar de forma eficiente.
</details>
<details> 
  <summary>Hint 2</summary>
  Podemos buscar lo descrito en el hint 1 letra por letra. Dado que hayamos precalculado el suffix array del string original, en este tendremos ordenados los sufijos. Todo substring debe ser el prefijo de un sufijo, luego basta buscar el sufijo que tenga un prefijo común más grande. Piensen cómo hacerlo letra por letra usando búsqueda binaria.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos buscar letra por letra con búsqueda binaria, inicialmente l = 0, r = N y tenemos todos los sufijos, hacemos búsqueda binaria por una letra y podemos reducir el rango a l', r' donde todos los sufijos en [l', r') comparten la primera letra con el string buscado, luego acotamos este nuevo rango según la segunda letra y así sucesivamente. En el momento donde no podamos encontrar una letra habremos encontrado el substring más largo posible, agregamos uno a la respuesta y empezamos de nuevo del rango [0, N) con la letra que quedamos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Matcomgrader/GluingPictures.cpp">Código de ejemplo</a>
</details>

### D - Lucky Common Subsequence
<details> 
  <summary>Hint</summary>
  Noten que si no existiera el virus, el problema de encontrar la mayor subsecuencia común se puede resolver usando un dp cuadrático con estados i, j, correspondientes a las posiciones que estamos revisando de cada string, luego la recursión es en (i, j) considerar dp(i + 1, j), dp(i, j + 1) y si S1[i] == S[j] considerar 1 + dp(i + 1, j + 1) (retornando el máximo). La respuesta es dp(0, 0). Piensen en cómo adaptar esta recursión para detectar cuando se complete un virus y evitarlo.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos usar un approach como KMP, en este algoritmo se recorre un string linealmente y se puede detectar cuando aparece otro string dentro, podemos usar este mismo método para detectar si con las letras que se han usado (cuando se pasó a (i + 1, j + 1) en la recursión) se arma el virus. Basta agregar un estado extra al dp que haga referencia al índice del arreglo lps actual.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/LuckyCommonSubsequence.cpp">Código de ejemplo</a>
</details>

### G - Match & Catch
<details> 
  <summary>Hint</summary>  
  Piensen en cómo se puede responder lo pedido usando el precálculo de un suffix array y lcp. Noten que todo substring es un prefijo de un sufijo, y para que sea único en el string original basta con que sea de largo mayor al lcp anterior y posterior (pues no habrá otro prefijo de sufijo igual de ese largo).
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos usar el hint 1 pero precalculando sobre el string S1#S2, así podemos filtrar los substrings comunes y unicos de ambos mirando el lcp, de forma que serán continuos en el suffix array pero los lcp inmediatamente posterior y anterior serán menores. Es decir, si estamos en la posición i del suffix array, donde sa[i] es parte de S1 y sa[i + 1] es parte de S2. luego el menor substring común asociado a esa posición debe ser de largo menor o igual a lcp[i], pero sólo será unico en ambos strings si lcp[i] >= largo > max(lcp[i - 1], lcp[i + 1]). Luego si es posible tomamos largo = max(lcp[i - 1], lcp[i + 1]) + 1, y nos quedamos con el menor de estos largos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MatchAndCatch.cpp">Código de ejemplo</a>
</details>

### H - String Similarity
<details> 
  <summary>Hint</summary>
  Noten que si calulamos el suffix array con arreglo lcp del string original ya se tiene calculado el tamaño de los longuest common preffix de sufijos continuos en el suffix array. Piensen en cómo ocupar esto para obtener la respuesta.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos buscar el lugar donde está el string completo en el suffix array (buscar la posición del 0). Luego la respuesta será la suma de acumular mínimos hacia derecha e izquierda del arreglo lcp, esto pues el largo común de un segmento continuo del suffix array corresponde al mínimo de los lcp del rango.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/HackerRank/StringSimilarity.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 9](../contests#contest-9) > ```{{page.title}}```
