---
title: contest 5 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```

### B - Tree 2
<details> 
  <summary>Hint 1</summary>
  Si supieramos cual es el nodo más lejano a nosotros, bastaría con ver si la distancia entre yo y el es mayor o igual a k, de serlo devolvemos el k-ésimo nodo en el camino y si no no existe nodo que cumpla lo pedido. Lamentablemente no podemos sacar distancias entre todos los nodos en tiempo, piensen en una forma de poder saber uno a mayor distancia rápidamente.
</details>
<details> 
  <summary>Hint 2</summary>
  Podemos obtener 2 nodos que esten lo más lejos posible uno del otro en el árbol. Basta con hacer 2 dfs ambos encontrando nodos más lejanos, el primero de un nodo cualquiera y el segundo del nodo encontrado más lejos en el primero (así encontramos el 2o). Estos dos nodos serán extremos de un diámetro de un árbol y es más, podemos demostrar que para cualquier nodo (u) en el árbol, se cumple que uno de los 2 nodos encontrados es lo más lejano a u posible. Usando esto y el hint 1 estamos casi listos. Sólo falta poder obtener distancia entre nodos y el k-ésimo en un camino rápidamente.
</details>
<details>
  <summary>Solución + código</summary>
  Para hacer lo último del hint 2 basta usar LCA, la distancia entre u y v es simplemente las profundidades de ambos nodos sumadas menos la profundidad del lca entre ellos. Para obtener el k-ésimo nodo por otro lado basta hacer binary lifting usando la información de la sparse table de ancestros en el LCA.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Timus/Tree2.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 5](../contests#contest-5) > ```{{page.title}}```
