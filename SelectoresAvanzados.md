**2. Selectores avanzados**

Utilizando solamente los selectores básicos de la sección anterior, es posible diseñar prácticamente cualquier página web. No obstante, CSS define otros selectores más avanzados que permiten simplificar las hojas de estilos.

Desafortunadamente, el navegador Internet Explorer 6 y sus versiones anteriores no soportaban este tipo de selectores avanzados, por lo que su uso no era común hasta hace poco tiempo. Si quieres consultar el soporte de los selectores en los distintos navegadores, puedes utilizar las siguientes referencias:

Lista completa de los selectores que soporta cada versión de cada navegador
Test online en el que puedes comprobar los selectores que soporta el navegador con el que realizas el test

**2.1. Selector de hijos**

Se trata de un selector similar al selector descendente, pero muy diferente en su funcionamiento. Se utiliza para seleccionar un elemento que es hijo directo de otro elemento y se indica mediante el "signo de mayor que" (>):

p > span { color: blue; }

<p\><span\>Texto1</span\></p\>

<p\><a href="#"\><span\>Texto2</span\></a\></p\>

En el ejemplo anterior, el selector p > span se interpreta como "cualquier elemento <span> que sea hijo directo de un elemento <p\>", por lo que el primer elemento <span\> cumple la condición del selector. Sin embargo, el segundo elemento <span\> no la cumple porque es descendiente pero no es hijo directo de un elemento <p\>.

El siguiente ejemplo muestra las diferencias entre el selector descendente y el selector de hijos:

p a { color: red; }

p > a { color: red; }

<p\><a href="#"\>Enlace1</a\></p\>

<p\><span\><a href="#"\>Enlace2</a\></span\></p\>

El primer selector es de tipo descendente y por tanto se aplica a todos los elementos <a\> que se encuentran dentro de elementos <p\>. En este caso, los estilos de este selector se aplican a los dos enlaces.

Por otra parte, el selector de hijos obliga a que el elemento <a\> sea hijo directo de un elemento <p\>. Por lo tanto, los estilos del selector p > a no se aplican al segundo enlace del ejemplo anterior.

**2.2. Selector adyacente**

El selector adyacente se emplea para seleccionar elementos que en el código HTML de la página se encuentran justo a continuación de otros elementos. Su sintaxis emplea el signo + para separar los dos elementos:

elemento1 + elemento2 { ... }

Si se considera el siguiente código HTML:

<body\>

<h1\>Titulo1</h1\>

<h2\>Subtítulo</h2\>

...

<h2\>Otro subtítulo</h2\>

...

</body\>

La página anterior dispone de dos elementos <h2\>, pero sólo uno de ellos se encuentra inmediatamente después del elemento <h1\>. Si se quiere aplicar diferentes colores en función de esta circunstancia, el selector adyacente es el más adecuado:

h2 { color: green; }

h1 + h2 { color: red }

Las reglas CSS anteriores hacen que todos los <h2\> de la página se vean de color verde, salvo aquellos <h2\> que se encuentran inmediatamente después de cualquier elemento <h1\> y que se muestran de color rojo.

Técnicamente, los elementos que forman el selector adyacente deben cumplir las dos siguientes condiciones:

elemento1 y elemento2 deben ser elementos hermanos, por lo que su elemento padre debe ser el mismo.
elemento2 debe aparecer inmediatamente después de elemento1 en el código HTML de la página.
El siguiente ejemplo es muy útil para los textos que se muestran como libros:

p + p { text-indent: 1.5em; }

En muchos libros, suele ser habitual que la primera línea de todos los párrafos esté indentada, salvo la primera línea del primer párrafo. Con el selector p \+ p, se seleccionan todos los párrafos de la página que estén precedidos por otro párrafo, por lo que no se aplica al primer párrafo de la página.

**2.3. Selector de atributos**

El último tipo de selectores avanzados lo forman los selectores de atributos, que permiten seleccionar elementos HTML en función de sus atributos y/o valores de esos atributos.

Los cuatro tipos de selectores de atributos son:

[nombre_atributo], selecciona los elementos que tienen establecido el atributo llamado nombre_atributo, independientemente de su valor.

[nombre_atributo=valor], selecciona los elementos que tienen establecido un atributo llamado nombre_atributo con un valor igual a valor.

[nombre_atributo~=valor], selecciona los elementos que tienen establecido un atributo llamado nombre_atributo y al menos uno de los valores del atributo es valor.

[nombre_atributo|=valor], selecciona los elementos que tienen establecido un atributo llamado nombre_atributo y cuyo valor es una serie de palabras separadas con guiones, pero que comienza con valor. Este tipo de selector sólo es útil para los atributos de tipo lang que indican el idioma del contenido del elemento.

A continuación se muestran algunos ejemplos de estos tipos de selectores:

/* Se muestran de color azul todos los enlaces que tengan

   un atributo "class", independientemente de su valor

   */
a[class] { color: blue; }

/* Se muestran de color azul todos los enlaces que tengan

   un atributo "class" con el valor "externo"
   */
a[class="externo"] { color: blue; }

/* Se muestran de color azul todos los enlaces que apunten
   al sitio "http://www.ejemplo.com"
   */
a[href="http://www.ejemplo.com"] { color: blue; }

/* Se muestran de color azul todos los enlaces que tengan
   un atributo "class" en el que al menos uno de sus valores
   sea "externo"

   */
a[class~="externo"] { color: blue; }

/* Selecciona todos los elementos de la página cuyo atributo
   "lang" sea igual a "en", es decir, todos los elementos en inglés
    */
 *[lang=en] { ... }

/* Selecciona todos los elementos de la página cuyo atributo
   "lang" empiece por "es", es decir, "es", "es-ES", "es-AR", etc.

   */ssss
*[lang|="es"] { color : red }
