---
title: contest 4 - hints y códigos de ejemplo
---
[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```

### A - K12 - Building Construction
<details> 
  <summary>Hint</summary>
  Problema hello world de ternary. Usar long long ints en C++ para evitar overflow del int.
</details>
<details> 
  <summary>Solución + código</summary>
  Usar ternary search para encontrar el valor al que hacer todos iguales, la función de costo debe sumar el costo para cada posición. La función es convexa y es fácil de implementar. <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/K12-BuildingConstruction.cpp">Código de ejemplo</a>
</details>

### B - Is This JEE
<details> 
  <summary>Hint</summary>
  Otro problema hello world de ternary.
</details>
<details> 
  <summary>Solución + código</summary>
  Ternary para encontrar el punto donde se minimiza la función. La función es convexa y es fácil de implementar. <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/CodeChef/IsThisJEE.cpp">Código de ejemplo</a>
</details>

### C - Closest Distance
<details> 
  <summary>Hint</summary>
  Notar que la función de distancia es convexa, así que podemos usar ternary.
</details>
<details> 
  <summary>Solución + código</summary>
  Ternary sobre la función de distancia para encontrar el momento donde la distancia es mínima. La función de distancia es una función del tiempo. Podemos buscar el mínimo en el rango [0, 1] (en t = 0 están al principio y en t = 1 estan al final de sus respectivos segmentos). Si nos movemos de un punto A en tiempo 0 a un punto B en tiempo 1, la posición en el tiempo t será (A * (1 - t) + B * t). <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Otros/ClosestDistance.cpp">Código de ejemplo</a>
</details>


### D - Keeping the Dogs Apart
<details> 
  <summary>Hint</summary>
  Si recorremos los 2 paths en paralelo de a tramos, donde cada tramo es un segmento del mismo largo en ambos paths, entonces dentro de cada tramo el problema se nos reduce al mismo problema "C - Closets Distance" (el problema C es una subrutina del problema D).
</details>
<details> 
  <summary>Solución + código</summary>
  Usamos la técnica de 2 punteros: un puntero en el path A y un puntero en el path B. Asumimos que ambos perros avanzan en línea recta lo máximo que pueden hasta que alguno de los 2 perros choca con el comienzo del siguiente segmento de su path. En este instante, uno de los 2 perros cambia de dirección. Entonces, en ese tramo básicamente los 2 perros avanzan en segmentos de recta del mismo largo, entonces podemos calcular la distancia más corta entre ambos perros en ese tramo con ternary search (usamos el problema C como subrutina acá). El perro que llegó al comienzo del siguiente segmento en su path cambia de dirección, así que hacemos que su puntero aumente en 1. El puntero del otro perro sigue donde mismo pero su ubicación actual queda "a mita de camino" dentro de su segmento actual. La solución final es el mínimo entre todos los ternary searches hechos. La implementación de este problema puede ser un poco complicada la primera vez si es que no tienen mucha experiencia con problemas de geometría 2D. Intenta hacerlo por tu cuenta la primera vez, y luego compara con la solución ejemplo. <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/KeepingTheDogsApart.cpp">Código de ejemplo</a>
</details>

### E - Race Time!
<details> 
  <summary>Hint</summary>
  Si dibujas las ecuaciones de recta en un gráfico de tiempo vs posición, notarás que la función máximo es convexa y la función mínimo es cóncava, entonces la resta es convexa. Así que se puede hacer ternary para encontrar el mínimo.
</details>
<details> 
  <summary>Solución + código</summary>
  Ternary para encontrar el tiempo donde la distancia es mínima. Hay que implementar la función f(T) y hacerle ternary. <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/CodeChef/RaceTime!.cpp">Código de ejemplo</a>
</details>


### F - Rocket Powered hovercraft
<details> 
  <summary>Hint 1</summary>
  Este es un poblema difícil que ocupa varios elementos de geometría, para llegar a la solución es necesario notar distintos detalles. En primer lugar, después de un poco de análisis se puede llegar a que cualquier solución óptima que ocupe algún giro, debe comenzar girando, de lo contrario siempre es posible demostrar que esta solución no es la óptima.
</details>
<details> 
  <summary>Hint 2</summary>
  Tomando lo anterior en cuenta podemos separar una trayectoria en 3 etapas. Sólo giro, giro y traslación (movimiento circular uniforme), y sólo traslación. Podemos notar que dado un giro inicial, sólo habrá a lo más una configuración de las siguientes 2 etapas que conllevan llegar al punto deseado.
</details>
<details> 
  <summary>Hint 3</summary>
  Dado un ángulo de giro inicial hay muchas formas de calcular el tiempo que este nos determina, para poder calcularlo noten que si dejamos de girar es necesario estar en una dirección que con sólo avanzar nos lleve al punto final. Tomando esto en cuenta podemos calcular el ángulo necesario a girar en la 2a etapa (giro y traslación) para quedar mirando al punto de destino. Para esto pueden usar herramientas de trigonometría respecto al centro del giro (Para esto basta notar que el radio de giro siempre será v / w).
</details>
<details> 
  <summary>Solución + código</summary>
  Si consideramos todo lo anterior, para resolver el problema nos basta realizar una búsqueda ternaria sobre todos los valores del giro inicial y decidir a partir del tiempo total que este nos determina, notar que sólo necesitamos considerar valores de giro a que a lo más nos lleven al ángulo inicial del punto a destino.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/RocketPoweredHovercraft.cpp">Código de ejemplo</a>
</details>

### G - Weakness and Poorness
<details> 
  <summary>Hint</summary>
  Nos piden calcular el x que minimice el máximo de los valores absolutos de sumas por intervalos en el arreglo, esto se reduce a calcular el máximo entre las sumas positivas y las sumas negativas. Para calcular por ejemplo las sumas positivas basta recorrer un arreglo linealmente y para cada i almacenar la mayor suma positiva continua que termina en i, el máximo de las sumas positivas por intervalo corresponderá al mayor numero almacenado.
  </details>
<details>
  <summary>Solución + código</summary>
  Nos podemos fijar que para un x muy pequeño o muy grande el valor buscado aumenta, por lo que debemos buscar un punto intermedio, esto lo podemos hacer con búsqueda ternaria. Intentamos con valores de x entre -10000 y 10000 por los lámites del problema y para comparar los valores intermedios e la búsqueda calculamos weakness para ese valor en particular usando el hint. Para adaptar el hint a sumas negativas simplemente se puede usar el inverso de los valores del arreglo luego de restar x.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/WeaknessAndPoorness.cpp">Código de ejemplo</a>
</details>

### H - Police Patrol
<details> 
  <summary>Hint 1</summary>
  Se puede probar que la minima distancia a recorrer puede ser alcanzada situando la estación en la posición de algún criminal.
</details>
<details> 
  <summary>Hint 2</summary>
  Dada una posición de la estación de policía podemos calcular la distancia necesaria a recorrer tomando grupos de a lo más m criminales desde los extremos, este grupo contribuirá a la distancia total 2 veces la distancia del más lejando de ellos a la estación.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos hacer una búsqueda ternaria entera sobre los índices de las posiciones de los criminales, ya que podemos alcanzar el óptimo tomando el cuenta el hint 1. Para cada posición en la búsqueda calculamos la distancia total que requiere usando lo expresado en el hint 2.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/PolicePatrol.cpp">Código de ejemplo</a>
</details>

### I - Devu and his Brother
<details> 
  <summary>Hint</summary>
  Notar que es fácil calcular la cantidad de pasos necesarios para hacer que el maximo de B se menor o igual a x y el minimo de A sea mayor o igual a x.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos hacer una búsqueda ternaria entera sobre los posibles valores que separan a ambos arreglos. Para calcular la cantidad de pasos necesarios para hacer que ese sea el separados es suficiente hacer pasadas lineales sobre los arreglos y calcular los pasos necesarios para arreglar las entradas que se salgan del borde definido por x.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/DevuAndHisBrother.cpp">Código de ejemplo</a>
</details>

### J - Chasing the Cheetahs
<details> 
  <summary>Hint</summary>
  Es equivalente al problema E - Race Time
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/ChasingTheCheetahs.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```
