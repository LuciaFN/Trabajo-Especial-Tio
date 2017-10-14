#Herencia
La herencia en CSS es el mecanismo mediante el cual determinadas propiedades de un elemento padre se transmiten a sus hijos
No todas las propiedades CSS son heredadas, porque algunas de ellas no tendría sentido que lo fueran.
Por ejemplo, los relacionados al tamaño de los elementos.
​
​
Lista completa de las propiedades de CSS, sí se heredan o no.
https://www.w3.org/TR/css-2010/#properties
​
​
​
​
​
##Herencia
Todos los elementos de un documento HTML heredan todas las propiedades heredables de su padre excepto el elemento raíz (html), que no tiene padre.

El valor por defecto para estas propiedades es inherit.

p { color: inherit; } /*valor por defecto, hereda el color del div, que lo hereda del body, que lo hereda del html*/

​
​
###Escribir menos código.

Si ponemos la font-family al elemento HTML, todos los elementos lo heredan, no tengo que reescribirlo para que otros lo tengan.

​
¿Que pasa cuando a un elemento tiene 2 estilos definidos pero diferentes?
​
​
​
​
​
##Cascada - Especificidad
Más específico es el selector, entonces ese es el estilo que se aplica.
​

Especificidad en selectores anidados
Lo que tiene clases es más específico que lo que no.
Si tienen la misma cantidad de clases, gana el que tiene más elementos para cumplir.
Especificidad en selectores anidados

##Cascada - Orden
Si dos declaraciones afectan al mismo elemento, tienen la misma importancia y la misma especificidad, la selección final es el orden en las fuentes.

La declaración que se ve después en las hojas de estilo "ganará" a las anteriores.
​

​
No hay colisiones, porque no coinciden las propiedades en CSS. Hay herencia de estilo.

.
