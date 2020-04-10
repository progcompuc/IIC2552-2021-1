---
title: contest 4 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```

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


<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 4](../contests#contest-4) > ```{{page.title}}```
