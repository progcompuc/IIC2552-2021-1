---
title: contest 6 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```

### F - Mixtures
<details> 
  <summary>Hint</summary>
  Podemos ver el problema desde el final del proceso hasta el principio, es decir, cual es el óptimo para las últimas 2 pociones que mezclemos? Sabemos que el humo que genera esta última mezcla sólo depende de los colores de las mezclas que contiene cada una, pero al poder juntarse sólo con adyacentes, necesariamente cada mezcla es la unión de un segmento contiguo de las pociones iniciales. Si pensamos el proceso de esta forma basta con tomar cada vez la opción que nos genere menos humo en generar estas "últimas pociones" y mezclarlas.
</details>
<details> 
  <summary>Solución + código</summary>
  Siguiendo lo expresado en el Hint, podemos hacer un DP sobre todos los segmentos contiguos de pociones iniciales, y para cada uno de estos el dp calcula el punto óptimo para unirlo, es decir cómo separar en 2 el segmento en cuestión de tal forma que si cada uno de los nuevos segmentos se mezcla de manera óptima, esta última mezcla genere la menor cantidad de humo (tomando en cuenta el humo óptimo de sus subsegmentos). Para calcular el humo de los subsegmentos basta ocupar la misma función dp sobre ellos.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/Mixtures.cpp">Código de ejemplo</a>
</details>

### G - Scuba diver
<details> 
  <summary>Hint</summary>
  Podemos pensar este problema como decidir cilindro por cilindro si es que es óptimo tenerlo en los tanques finales o no, de esta forma se puede pensar la decisión de cada cilindro como subproblema, donde esta depende del peso óptimo para tener el oxígeno y nitrógeno restante (suponiendo que tomaste el tanque).
</details>
<details> 
  <summary>Solución + código</summary>
  Tomando en cuenta el hint, podemos pensar en hacer las elecciones en orden, es decir, podemos hacer un dp que dependa de 3 variables, indice, oxígeno a llevar y nitrógeno a llevar, y el índice indica que decidiremos sobre el i-ésimo tanque considerando sólo los tanques con índices mayores o iguales a i. Esto no cambia el resultado, pues cualquier configuración de tanques puede ser elegida en orden. Luego para cada subproblema hay dos opciones, llevar o no el i-ésimo tanque, si no lo llevamos el subproblema es equivalente al dp desde i+1 con los mismos requerimientos de oxígeno y nitrógeno. Pero si lo llevamos la respuesta es el peso del tanque más el óptimo desde i+1 de los requerimientos quitándole el aporte del tanque i.
  De esta forma la respuesta puede ser accedida desde el subproblema desde el primer índice y los requerimientos iniciales.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/SPOJ/ScubaDiver.cpp">Código de ejemplo</a>
</details>

### H - Greenhouse Effect
<details> 
  <summary>Hint 1</summary>
  Un primer insight es darse cuenta de que al poder colocar las plantas en el lugar que queramos, las coordenadas de estas no son realmente importantes para el problema, sólo el orden inicial de los tipos.
</details>
<details> 
  <summary>Hint 2</summary>
  Podemos descomponer el problema en subproblemas que deciden para cada planta si es óptimo moverla o no, y retornar la opción que desencadene menos movimentos al largo plazo.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución de este problema es similar a la del problema G. Podemos hacer un dp que dependa de 2 cosas, indice de la planta que decidiremos ahora y el mayor de los tipos de planta que hemos no movido (en cuanto a su tipo, no coordenadas). Recorremos los problemas de izquierda a derecha, decidiendo para cada planta en el dp, de esta forma el óptimo para un subproblema depende de los óptimos de los subproblemas siguientes. Nos importa el mayor de los tipos que no hemos movido en las plantas que ya decidimos, pues si este tipo es mayor que el de la planta que decidimos ahora, no podemos no moverla pues no generaría una configuración deseada.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/GreenhouseEffect.cpp">Código de ejemplo</a>
</details>

### I - Changing A String
<details> 
  <summary>Hint</summary>
  Podemos pensar el problema como ir igualando los strings de a poco de izquierda a derecha, de esta forma podemos definir un subproblema del dp como minimizar la cantidad de movimientos dado que estoy en el el índice i del primer string y en el índice j del segundo (asumes que ya igualaste lo anterior).
</details>
<details> 
  <summary>Solución + código</summary>
  Hacemos lo que dice el Hint. Para cada subproblema el mínimo es el que genere menos pasos de todas las opciones que tengan sentido, entre insertar, reemplazar, borrar o avanzar, que desencadenan a su vez una cantidad de movimientos que dependen de los siguientes subproblemas. Finalmente para recuperar los pasos de una estrategia óptima basta ir recorriendo las decisiones óptimas usando los valores que quedaron guardados en el memo. Es recomendable usar una funcion recursiva similar a la del dp para este último paso.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Codeforces/ChangingAString.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 6](../contests#contest-6) > ```{{page.title}}```
