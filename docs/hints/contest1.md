---
title: contest 1 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 1](../contests#contest-1) > ```{{page.title}}```

### A - Stones on the Table
<details> 
   <summary>Hint</summary>
   Basta recorrer el string y sumar uno a la respuesta cada vez que una letra sea igual a la anterior
</details>
<details>
   <summary>Solución + código</summary>
   Implementar el hint
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/StonesOnTheTable.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/StonesOnTheTable.cpp">Código de ejemplo C++</a>
</details>

### B - Sum of the Others
<details> 
   <summary>Hint</summary>
   Piensen en cuanto debe ser la suma de todo (incluyendo el resultado) si el resultado es igual a la suma
</details>
<details>
   <summary>Solución + código</summary>
   Implementar el hint. Para recibir lineas hasta que se acaben en python pueden usar la libreria sys y un for line in sys.stdin. Por otro lado en C++ pueden usar while (getline(cin, line)) y para separar los números en cada linea pueden usar stringstreams (averiguar).
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/SumOfTheOthers.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/SumOfTheOthers.cpp">Código de ejemplo C++</a>
</details>

### C - Maximum Square
<details> 
   <summary>Hint</summary>
   Piensen en cómo ayudaría ordenar las tablas de menor a mayor (o viceversa).
</details>
<details>
   <summary>Solución + código</summary>
   Si están ordenadas de menor a mayor y se recorren en ese orden, la primera vez que las tablas que quedan sean menos o igual al valor actual, las tablas que queden serán la respuesta.
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MaximumSquare.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/MaximumSquare.cpp">Código de ejemplo C++</a>
</details>

### D - Temporarily unavailable
<details> 
   <summary>Hint</summary>
   Podemos chequear si no hay intersección y retornar 0 (basta ver si el comienzo de cobertura esta después del final del recorrido o si el final del radio de cobertura está antes del inicio del recorrido), en otro caso basta sumar el tamaño del principio al comienzo del radio de cobertura y del final del radio de cobertura hasta el final del recorrido (si son positivos).
</details>
<details>
   <summary>Solución + código</summary>
   Implementar el hint.
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TemporarilyUnavailable.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TemporarilyUnavailable.cpp">Código de ejemplo C++</a>
</details>

### E - H-Index
<details> 
   <summary>Hint</summary>
   Se debe encontrar el mayor H tal que tenemos al menos H papers con al menos H citas. Para esto piensen cómo facilita el cálculo ordenar las citas de cada paper de mayor a menor. Ojo que no se puede resolver viendo todas las posibilidades de H y chequeando porque no pasa en el tiempo límite.
</details>
<details>
   <summary>Solución + código</summary>
   Dado que lo tenemos ordenado de mayor a menor, para cada posición i en la lista de citas C (de 0 a N - 1) la respuesta será el máximo de calcular min(C[i], i + 1). Esto pues min(C[i], i + 1) representa el mayor número que cumple que hay al menos esa cantidad de papers con al menos esa cantidad de citas para cada posición.
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/H-Index.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/H-Index.cpp">Código de ejemplo C++</a>
</details>

### F - Center Alignment
<details> 
   <summary>Hint</summary>
   Basta implementar lo descrito en el enunciado. Cuidado con los casos especiales de alineamiento, si hay una cantidad impar de espacio, se da menos espacio a la izquierda primero, la próxima vez con espacios impares a la derecha y así.
</details>
<details>
   <summary>Solución + código</summary>
   Implementar el hint.
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/CenterAlignement.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/CenterAlignement.cpp">Código de ejemplo C++</a>
</details>

### G - Four Segments
<details> 
   <summary>Hint</summary>
   Busque características necesarias y suficientes para determinar que los segmentos entregados forman un rectángulo, por ejemplo, hay exactamente 4 puntos y 4 segmentos, 2 verticales y 2 horizontales.
</details>
<details>
   <summary>Solución + código</summary>
   Implementar el hint.
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/FourSegments.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/FourSegments.cpp">Código de ejemplo C++</a>
</details>

### H - Touchscreen Keyboard
<details> 
   <summary>Hint</summary>
   Podemos asignarles coordenadas de fila y columna a cada letra. Usando esto es fácil obterner la solución calculando distancias y ordenando. Pueden guardar las coordenadas en un diccionario de python o en un map de c++.
</details>
<details>
   <summary>Solución + código</summary>
   Implementar el hint.
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/TouchscreenKeyboard.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/TouchscreenKeyboard.cpp">Código de ejemplo C++</a>
</details>

### I - Adding Words
<details> 
   <summary>Hint</summary>
   Pueden usar diccionarios de Python o maps de c++ para asignar valores a las palabras y palabras a los valores. Usando esto piensen en cómo implementar el resto.
</details>
<details>
   <summary>Solución + código</summary>
   Usando el hint, en caso de definición sólo asignamos, en caso de clear limpiamos los diccionarios y en caso de cálculo se va sumando el valor multiplicado por signo anterior hasta encontrar un igual. Ojo ir chequeando que existan las keys en los maps. Hay un caso borde al volver a asignar una palabra previamente asignada, en este caso deben borrar la asignación del valor anterior a la palabra.
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/AddingWords.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/AddingWords.cpp">Código de ejemplo C++</a>
</details>

### J - They Are Everywhere
<details> 
   <summary>Hint</summary>
   Hay varias formas de hacerlo, una de las más simple consiste en mantener un rango en que están presentes todos los pokemons para cada posición final. Empezando de la primera posición en que estén todos los pokemons hacia la izquierda, si avanzamos el borde derecho en una posición podemos mover el izquierdo mientras la ocurrencia del pokemon en el borde izquierdo dentro del rango sea mayor a 1. La respuesta final será el mínimo de estos rangos. Está técnica es una aplicación de dos punteros y es un enfoque bastante usado en programación competitiva.
</details>
<details>
   <summary>Solución + código</summary>
   Implementar el hint.
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TheyAreEverywhere.py">Código de ejemplo Python</a>
   
   <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/TheyAreEverywhere.cpp">Código de ejemplo C++</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 1](../contests#contest-1) > ```{{page.title}}```
