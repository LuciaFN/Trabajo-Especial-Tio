
#Selectores, Cascada y Colisiones

Qué sabemos hasta ahora de CSS?
Sirve para aplicar el estilo a una página web.
Se escribe en un archivo aparte del HTML con extensión .css
Para seleccionar elementos de HTML tenemos 3 tipos de selectores:
Tipo (p, h1, div, etc.)
Clase
Id
​
##Selector Universal


Se utiliza para seleccionar todos los elementos de la página.

El siguiente ejemplo elimina el margen y el relleno de todos los elementos HTML.
Pregunta
​
​
¿Cómo hacemos para aplicar un estilo solo a los párrafos con clase ‘destacado’?
​
##Combinación de Selectores
​
Se pueden combinar selecciones para hacerlas más específicas.
​
​
Elige los párrafos que contengan la clase “destacado”.
​
De lo anterior se deduce que el atributo .destacado es equivalente a *.destacado, por costumbre todos obvian el símbolo * al escribir un selector de clase normal.
​
Lo mismo se aplica a Ids.
p#uno { font-size: 25px; }

​​
​​
Combinación de Selectores

​
div > p {

background-color: yellow;

}

​
Selecciona todos los elementos <p> que son hijos inmediatos (el 1er hijo) de un elemento <div\>.

​
div + h2 {

background-color: red;

}

​
Selecciona todos los elementos <h2\> que están inmediatamente a continuación de un div. Sería el hermano <h2\> siguiente adyacente a <div\>

​
p ~ h2 {

background-color: orange;

}

​
Selecciona todos los hermanos de <p\> que sean <h2\>

​
Ejemplo - Selectores Combinados

​
###Mejorando el código CSS

​
###Grupo de Selectores


Se pueden usar varios selectores juntos.
Esto permite evitar duplicación de estilos.
Además se pueden refinar las diferencias aparte
Se separan los selectores con ‘,’ creando un grupo de selectores con propiedades en común

​
¿Qué ventajas ven de re-usar estilos?

​
Cuidado #1

Un espacio o una coma puede hacer la diferencia!

Cuidado #2

Un espacio o una coma puede hacer la diferencia!
