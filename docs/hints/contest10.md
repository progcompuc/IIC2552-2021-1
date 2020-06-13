---
title: contest 10 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 10](../contests#contest-10) > ```{{page.title}}```

### D - Geophysics Prospection
<details> 
  <summary>Hint</summary> 
  Para poder contar agrupaciones de elementos iguales podemos usar un dfs que cuente los elementos de cada componente, si hacemos un dfs en cada componente que pase su tamaño sólo debemos ordenar para obtener la respuesta. Para esto hay que tener cuidado de no repetir necesariamente los dfs que se realizan.
</details>
<details> 
  <summary>Solución + código</summary>
  Podemos hacer dfs al estilo contar componentes conexas, vamos por cada celda, si no la hemos visitado hacemos un dfs que sólo recorrerá celdas de ese tipo y guardamos el tamaño que recorre, y seguimos así. Al final basta con encontrar alguna manera de ordenar los tamaños obtenidos para devolver como se pide. Una opción es hacer uso de priority queues para cada tipo de material.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/ICPC/GeophysicsProspection.cpp">Código de ejemplo</a>
</details>


<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 10](../contests#contest-10) > ```{{page.title}}```
