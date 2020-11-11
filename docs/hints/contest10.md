---
title: contest 10 - hints y códigos de ejemplo
---

[Index](../index) > [Contests](../contests) > [Contest 10](../contests#contest-10) > ```{{page.title}}```

### A - Treasure Spotting
<details> 
  <summary>Hint 1</summary>
  Se debe chequear para cada pirata la visibilidad del tesoro, para eso debemos chequear tres cosas, que el tesoro esté en el semidisco visible para el pirata, que para toda muralla no lo tape y que para todo otro pirata no lo tape. Si podemos hacer cada chequeo en tiempo constante el algoritmo pasará en tiempo.
</details>
<details> 
  <summary>Hint 2</summary>
  Para chequear que el tesoro se encuentra en el semidisco de visión basta ver que este a una distancia menor o igual a la del radio entregado por input (se calcula como la distancia entre los puntos entregados para el pirata en R2) y que además el producto punto entre el vector de visión entregado AB y el vector al tesoro AT sea mayor o igual a 0.
</details>
<details> 
  <summary>Hint 3</summary>
  Para chequear que cada muralla no tape basta con chequear si los segmentos AT y CD intersectan, donde AT es del pirata al tesoro y CD es la muralla. Para chequear intersección de segmentos se puede ver que para cada segmento, los puntos del otro segmento estén a lados distintos de la recta generada por el segmento analizado, si esto pasa para ambos hay intersección. También habrá intersección si alguno de los puntos de un segmento está en el otro segmento.
</details>
<details> 
  <summary>Solución + código</summary>
  La solución consiste en usar los hints e implementarlo correctamente teniendo en cuenta la precisión, para evitar problemas evitar el uso de doubles a menos que se considere pequeñas variaciones.
  <a href="https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Problems/Kattis/TreasureSpotting.cpp">Código de ejemplo</a>
</details>

<!-- <details> 
  <summary>Hint</summary>   
</details>
<details> 
  <summary>Solución + código</summary>
  <a href="">Código de ejemplo</a>
</details> -->

[Index](../index) > [Contests](../contests) > [Contest 10](../contests#contest-10) > ```{{page.title}}```
