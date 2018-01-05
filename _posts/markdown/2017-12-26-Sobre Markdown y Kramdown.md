---
layout: post
title:  "Kramdown"
lang: es
ref: markdown
date: 2017-12-26 09:48:44 +0100
autor: Saltw
categories: markdown
tags: [Kramdown, Markdown]
description: Kramdown es una librería en Ruby para convertir Markdown a XHTML. Guía de sintáxis de Markdown para convertir fácilmente tus publicaciones en código web semántico.
robots: NoIndex, Follow
---


[**Kramdown**](https://kramdown.gettalong.org/) es una librería en [Ruby](https://www.ruby-lang.org/es/) para procesar y convertir **Markdown** a HTML. La librería, ademas de Kramdown, puede interpretar Markdown, [Github Flavored Markdown](https://guides.github.com/features/mastering-markdown/) y HTML


## ¿Qué es Markdown?

[**Markdown**](https://daringfireball.net/projects/markdown/) es un lenguaje de marcado ligero parecido al que se emplea en muchas wikis y basado originalmente en convenciones existentes en el marcado de los los correos electronicos. Emplea texto plano, procurando que sea legible pero consiguiendo que se convierta en XHTML correctamente formateado.

Permite controlar fácilmente la visualización del documento en la web creando documentos XHTML limpios y fácilmente editables en el futuro sin ningún conocimiento en programación.

Dar formato a las palabras en **negrita** o _cursiva_, insertar enlaces internos ó externos, insertar imágenes, redactar con títulos, blockquotes, listas, definiciones o tablas son sólo algunas de las cosas que puedes hacer con Markdown.\\
En su mayoría, Markdown sólo es texto normal con algunos caracteres no alfabéticos como ```#``` o ```*```.


Sumario

1. [Párrafos](#párrafos)
1. [Encabezados](#encabezados)
1. [Saltos de línea](#saltos-de-línea)
1. [Línea horizontal](#línea-horizontal)
1. [Énfasis](#énfasis)
1. [Citas](#citas)
1. [Bloques de código](#bloques-de-código)
1. [Listas](#listas)
    1. [Ordenadas](#ordenadas)
    1. [Desordenadas](#desordenadas)
    1. [Listas de definiciones](#listas-de-definiciones)
1. [Enlaces](#enlaces)
    1. [Enlaces externos](#enlaces-externos)
    1. [Enlaces internos](#enlaces-internos)
        1. [A párrafos de la página actual](#a-párrafos-de-la-página-actual)
        1. [A párrafos de otras páginas de tu web](#a-párrafos-de-otras-páginas-de-tu-web)
1. [Imágenes](#imágenes)
1. [Tablas](#tablas)
1. [Notas a pie de página](#notas-a-pie-de-página)
1. [Abreviaturas](#abreviaturas)
1. [Atributos HTML](#atributos-html)


## Sintáxis básica Kramdown

[original](https://kramdown.gettalong.org/quickref.html)

Abajo se describe de forma general de la sintaxis de Markdown que puedes usar en tus propios archivos de texto.

Los caracteres comodín de Markdown que a continuación se detallan como transformadores de texto (como ```#``` o ```*```) serán interpretados de forma literal para su uso si se preceden por una barra invertida ```\```.

A saber, la secuencia ```\*``` mostrará un asterisco en lugar de empezar una sección de texto en negrita o una lista desordenada.

Comencemos...


### Párrafos
Las líneas de texto consecutivas se consideran un párrafo.

Escribiendo esto

>   Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

... tus usuarios ven ...

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

... y se programa así

``` html
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
```


### Encabezados

Se usa la almohadilla para indicar el nivel del titulo.

Escribiendo esto

>   # Encabezado h1 (Título del sitio web)\\
>   ## Encabezado h2 (Título de la página)\\
>   ### Encabezado h3 (Sección de página)\\
>   #### Encabezado h4 (Subsección)\\
>   ##### Encabezado h5 (Subsub)\\
>   ###### Encabezado h6 (subsubsub)

... tus usuarios ven ...

``` Encabezado h1 (Título del sitio web) -anulado. Nivel superior -```
## Encabezado h2 (Título de la página)
### Encabezado h3 (Sección de página)
#### Encabezado h4 (Subsección)
##### Encabezado h5 (Subsub)
###### Encabezado h6 (subsubsub)

... y se programa así

``` html
<h1>Encabezado h1 (Título del sitio web)</h1>
<h2>Encabezado h2 (Título de la página)</h2>
<h3>Encabezado h3 (Sección de página)</h3>
<h4>Encabezado h4 (Subsección)</h4>
<h5>Encabezado h5 (Subsub)</h5>
<h6>Encabezado h6 (subsubsub)</h6>
```


#### Saltos de línea

a). Separando párrafos con una ó mas línea/s en blanco entre párrafos.

Escribiendo esto

> Quien fue a sevilla
>
> perdió su silla

... tus usuarios ven ...

    Quien fue a sevilla

    perdió su silla

... y se programa así

``` html
<p>Quien fue a sevilla</p>

<p>perdió su silla</p>
```

b). Añadiendo `\\` al final de línea.

Escribiendo esto

> `Quien fue a Sevilla\\`
> `perdió su silla`

... tus usuarios ven ...

    Quien fue a Sevilla
    perdió su silla

... y se programa así

``` html
<p>Quien fue a Sevilla<br />
perdió su silla</p>
```

c). Añadiendo dos espacios en blanco correlativos al final de línea.


### Línea horizontal

Las líneas horizontales se crean con tres guiones

Escribiendo esto

> `---` ó\\
> `***` ó\\
> `___`

... tus usuarios ven ...

---

... y se programa así

``` html
<hr />
```


### Énfasis

```*Este texto se verá en cursiva*``` *Este texto se verá en cursiva*\\
```_Este texto también se verá en cursiva_``` _Este texto también se verá en cursiva_\\
```**Este texto se verá en negrita**``` **Este texto se verá en negrita**\\
```__Este texto también se verá en negrita__``` __Este texto también se verá en negrita__\\
```_También **puedes combinar** ambos_``` _También **puedes combinar** ambos_\\
```**También _puedes combinar_ ambos**``` **También _puedes combinar_ ambos**

... y se programa así

``` html
<em>Este texto se verá en cursiva</em>
<em>Este texto también se verá en cursiva</em>
<strong>Este texto se verá en negrita</strong>
<strong>Este texto también se verá en negrita</strong>
<em>También <strong>puedes combinar</strong> ambos</em>
<strong>También <em>puedes combinar</em> ambos</strong>
```

:warning:   **¡Importante!** Usa con sabiduría **negrita** y _cursiva_ en tu página 100% semántica.
1. **Negrita** ~ (`<strong>` para los navegadores) representa un **texto especialmente importante** y así se guardará en las bases de datos de buscadores como Google.
    * Deberías utilizarla para maquetar tu artículo con las palabras y frases claves acorde a tu publicación para que los buscadores la posicionen en consecuencia.
    * En un artículo de pesca, p.ej., es beneficioso resaltar en negrita **salmón**, **la pesca del salmón**, **temporada de salmón**, **el mejor anzuelo para salmón**, etc.
    * Perjudicará tu posicionamiento resaltar términos como **coche**, **sin cebolla** ó **sesión bermut**, porque el Buscador restará importancia a la semántica de título al indexarlo con otros temas de propósito general como anécdotas o experiencias personales con salmones.
1. _Cursiva_ ~ (`<em>` para los navegadores) Representa un **texto enfatizado, con un acento de intensidad**. Tanto en la imaginación de tus usuarios como con un cambio de tono en los lectores de pantalla (p.ej. en el software de acceso para ciegos).
    * Aunque la costumbre se restringe a términos técnicos, nombres propios o referencias puedes usarla para dar __musicalidad__ a tus publicaciones y mejorar la experiencia de usuario con humor, cercanía o complicidad.


### Citas o blockquotes

Se comienza un blockquote usando el marcador "mayor que" (`>`) seguido de un espacio opcional.

todas las líneas siguientes que también se inician con el marcador de blockquote pertenecen a su blockquote.

Se puede usar subniveles dentro del blockquote.

Escribiendo esto

```
> Esta es una cita de bloque de muestra
>
> > Puedes anidar blockquotes
```

... tus usuarios ven ...


> Esta es una cita de bloque de muestra
>
> > Puedes anidar blockquotes

... y se programa así

``` html
<blockquote>
  <p>Esta es una cita de bloque de muestra</p>

  <blockquote>
    <p>Puedes anidar blockquotes</p>
  </blockquote>
</blockquote>
```


### Bloques de código

Se pueden crear bloques de código para albergar extractos de código fuente de un lenguaje de programación o para reproducir literalmente cualquier tipo de texto sin que sea interpretado por markdown.

1. Precediendo el párrafo por 4 espacios en blanco o un tabulado
1. Encerrando el párrafo entre dos línas con trés caracteres tilde (`~~~`)
1. Encerrando el texto entre dos acentos graves (`)


Escribiendo esto

>  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Esto es un bloque de código

>  \~\~\~\\
>  Esto es otro bloque de código\\
>  \~\~\~


>  \`Esto del un bloque de código en línea\`


... tus usuarios ven ...

    Esto es un bloque de código

~~~
Esto es otro bloque de código
~~~

`Esto del un bloque de código en línea`


... y se programa así

``` html
<p><code class="highlighter-rouge">Esto del un bloque de código en línea</code></p>
```


### Listas

Puede crear listas ordenadas y listas desordenadas.

#### Ordenadas

Utilizan el número, un punto y un espacio seguido del ítem.

Escribiendo esto

> `1. Item 1`\\
> `1. Item 2`\\
> `1. Item 3`\\
> > `1. Item 3a`\\
> > `1. Item 3b`

... tus usuarios ven ...

1. Item 1
1. Item 2
1. Item 3
    1. Item 3a
    1. Item 3b

... y se programa así

``` html
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3
    <ol>
      <li>Item 3a</li>
      <li>Item 3b</li>
    </ol>
  </li>
</ol>
```

#### Desordenadas

Se puede utilizar `*`, `+` ó `-`, seguidos de un espacio en blanco.
También se pueden anidar.

Escribiendo esto

> * Un elemento en una lista no ordenada
> * Otro elemento de la lista
> >    * sub-ítem 1
> >    * sub-ítem 2
> >    * sub-ítem 3
> > >    * subsub 1

... tus usuarios ven ...

* Un elemento en una lista no ordenada
* Otro elemento de la lista
    * sub-ítem 2a
    * sub-ítem 2b
    * sub-ítem 2c
        * subsub 2c1

... y se programa así

``` html
<ul>
  <li>Un elemento en una lista no ordenada</li>
  <li>Otro elemento de la lista
    <ul>
      <li>sub-ítem 2a</li>
      <li>sub-ítem 2b</li>
      <li>sub-ítem 2c
        <ul>
          <li>subsub 2c1</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>
```


#### Listas de definiciones

Las listas de definición apenas se utilizan en la mayoría de páginas web.

Su funcionamiento es similar al de un diccionario, ya que cada elemento de la lista está formado por términos y definiciones. La etiqueta <dl> crea la lista de definición y las etiquetas <dt> y <dd> definen respectivamente el término y la descripción de cada elemento de la lista.

Primeramente se escribe el término y en una nueva línea su definicion precedida de dos puntos (`:`)

Escribiendo esto

> `Término`\\
>   `: definición principal`\\
>   `: otra definición`

... tus usuarios ven ...

Término
: definición principal
: otra definición

... y se programa así

``` html
<dl>
  <dt>Término</dt>
  <dd>definición principal</dd>
  <dd>otra definición</dd>
</dl>
```


### Enlaces

#### Enlaces externos

Se puede crear un enlace simple rodeando el texto con corchetes y el enlace URL con paréntesis

Escribiendo esto

> `Practica con textos [Lorem Ipsum](http://www.loremipsum.es/) los ejemplos de esta guía básica.`

... tus usuarios ven ...

Practica con textos [Lorem Ipsum](http://www.loremipsum.es/) los ejemplos de esta guía básica.

... y se programa así

``` html
<p>Practica con textos <a href="http://www.loremipsum.es/">Lorem Ipsum</a> los ejemplos de esta guía básica.</p>
```

#### Enlaces internos

##### A párrafos de la página actual

Los encabezados crean automáticamente anclas en la salida html renderizada resultante. También puedes tus propios identificadores de cabecera que tendrá prioridad sobre los id's automáticos

> `{#cabecera1}`

Puedes vincular cualquier encabezado único usando la sintáxis de enlace precedida de almohadilla `(#)`, recordando convertir el encabezado a formato URI

:paperclip: **Nota:** Observa los ejemplos y convierte tu link a URI, a saber; letras minúsculas y sustituyendo los espacios por guiones (`-`)

Escribiendo esto

> `Véase [Enlaces externos](#enlaces-externos)`

... tus usuarios ven ...

Véase [Enlaces externos](#enlaces-externos)

... y se programa así

``` html
<p>Véase <a href="#enlaces-externos">Enlaces externos</a></p>
```

##### A párrafos de otras páginas de tu web

Similar al anterior

> `Véase [Enlaces externos](https://mi-sitio-web.ext/blog/permalink.html/#enlaces-externos)`

, pero anteponiento la ruta completa a la publicación que contiene el título referenciado

Escribiendo esto

> `Copia este [Pasaje estándar Lorem Ipsum](https://mi-sitio-web.ext/blog/que-es-lorem-ipsum.html/#el-pasaje-estándar-lorem-ipsum-usado-desde-el-año-1500) para practicar los ejemplos de esta guía básica.`

... tus usuarios ven ...

Copia este [Pasaje estándar Lorem Ipsum]({{ "/blog/que-es-lorem-ipsum.html/#el-pasaje-estándar-lorem-ipsum-usado-desde-el-año-1500" | append: site.baseurl }}) para practicar los ejemplos de esta guía básica.

... y se programa así

``` html
<p>Copia este <a href="/blog/que-es-lorem-ipsum.html/#el-pasaje-estándar-lorem-ipsum-usado-desde-el-año-1500">Pasaje estándar Lorem Ipsum</a> para practicar los ejemplos de esta guía básica.</p>
```


### Imágenes

De forma similar a los enlaces, se inician con un signo de exclamación seguido por el [texto alternativo de la imágen](https://www.w3schools.com/tags/att_img_alt.asp) entre corchetes y el enlace URL entre paréntesis.

`![Google! agrúpame como imágen de fútbol y puesta de sol](http://lorempixel.com/output/sports-q-c-640-480-6.jpg)`

![[Google! agrúpame como imágen de fútbol y puesta de sol](http://lorempixel.com/output/sports-q-c-640-480-6.jpg)\\


### Tablas

**Kramdown** admite una sintaxis para crear tablas simples.

Crear tablas es sumamente sencillo, simplemente debemos indicar cuales son los elementos de la cabecera y separar los campos con el símbolo de tubería (`|`)

Por costumbre, se suelen alinear las columnas e incluso comenzar y finalizar las filas con el símbolo |, pero no es en absoluto necesario.

Las líneas separadoras se usan para dividir el encabezado de la tabla del cuerpo de la tabla (y opcionalmente alinear las columnas de la tabla) y para dividir el cuerpo de la tabla en varias partes.

1. Un carácter de tubería seguido de un guion (`|-`), crea una línea de separación.
1. Un carácter de tubería seguido por un signo igual (`|=`), crea el pie de tabla.

Se puede especificar la alineación de cada columna mediante la adición de dos puntos a las líneas de separación.

1. Dos puntos a la izquierda de la línea de separación (`|:--|`) hará que la columna esté alineada a la izquierda,
1. dos puntos a la derecha de la línea (`|--:|`)  hará que la columna esté alineada a la derecha,
1. dos puntos en ambos lados significa (`|:--:|`) que la columna se alinea al centro.

Escribiendo esto

> `| &nbsp;Header A&nbsp; | &nbsp;Header B&nbsp; | &nbsp;Header C&nbsp; |`\\
> `|:--------|:-------:|--------:|`\\
> `| cell 1a | cell 1b | cell 1c |`\\
> `| cell 2a | cell 2b | cell 2c |`\\
> `|----`\\
> `| cell 3a | cell 3b | cell 3c |`\\
> `| cell 4a | cell 4b | cell 4c |`\\
> `|=====`\\
> `| Footer A | Footer B | Footer C`\\
> `{: rules="groups"}`

... tus usuarios ven ...

| &nbsp;Header A&nbsp; | &nbsp;Header B&nbsp; | &nbsp;Header C&nbsp; |
|:--------|:-------:|--------:|
| cell 1a | cell 1b | cell 1c |
| cell 2a | cell 2b | cell 2c |
|----
| cell 3a | cell 3b | cell 3c |
| cell 4a | cell 4b | cell 4c |
|=====
| Footer A | Footer B | Footer C
{: rules="groups"}

... y se programa así

``` html
<table rules="groups">
  <thead>
    <tr>
      <th style="text-align: left"> Header A </th>
      <th style="text-align: center"> Header B </th>
      <th style="text-align: right"> Header C </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left">cell 1a</td>
      <td style="text-align: center">cell 1b</td>
      <td style="text-align: right">cell 1c</td>
    </tr>
    <tr>
      <td style="text-align: left">cell 2a</td>
      <td style="text-align: center">cell 2b</td>
      <td style="text-align: right">cell 2c</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <td style="text-align: left">cell 3a</td>
      <td style="text-align: center">cell 3b</td>
      <td style="text-align: right">cell 3c</td>
    </tr>
    <tr>
      <td style="text-align: left">cell 4a</td>
      <td style="text-align: center">cell 4b</td>
      <td style="text-align: right">cell 4c</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td style="text-align: left">Footer A</td>
      <td style="text-align: center">Footer B</td>
      <td style="text-align: right">Footer C</td>
    </tr>
  </tfoot>
</table>
```

:paperclip: **Nota:** `&nbsp;` imprime un espacio en blanco


### Notas a pie de página

Cada nota de pie de página se compone de dos elementos; un marcador al lado del texto que se convierte en un superíndice y de una definición que se puede colocar en una lista de notas al pie al final de documento.


Escribiendo esto

>  `Esto es un texto con nota a pie de página [^1]`
>
>  `[^1]: Esta es la nota 1 a pie de página.`

... tus usuarios ven ...

Esto es un texto con nota a pie de página [^1]

[^1]: Esta es la nota 1 a pie de página.


... y se programa así

``` html
<p>Esto es un texto con nota a pie de página <sup id="fnref:1"><a href="#fn:1" class="footnote">1</a></sup></p>

<div class="footnotes">
  <ol>
    <li id="fn:1">
      <p>Esta es la nota 1 a pie de página. <a href="#fnref:1" class="reversefootnote">&#8617;</a></p>
    </li>
  </ol>
</div>
```


### Abreviaturas


Para crear abreviaturas HTML lo único necesario es crear una lista de ellas (normalmente al final del texto) y en cualquier lugar de la página en la que el texto que aparezca la abreviatura se aplicará automáticamente.

Las listas de abreviaturas se crean como las listas de enlaces, pero precedidas por un asterisco.

Las abreviaturas son sensibles a mayúsculas, por lo que hay que tenerlo en cuenta. Se pueden crear abreviaturas de más de una palabra.

Escribiendo esto

>  `Puedes crear una versión de tu CV en PDF.`\\
>  `*[CV]: Curriculum Vitae`\\
>  `*[PDF]: Formato de Documento Portátil`

... tus usuarios ven ...

Puedes crear una versión de tu CV en PDF

*[CV]: Curriculum Vitae
*[PDF]: Formato de Documento Portátil

... y se programa así

``` html
<p>Puedes crear una versión de tu <abbr title="Curriculum Vitae">CV</abbr> en <abbr title="Formato de Documento Portátil">PDF</abbr></p>
```


### Atributos html

Son modificadores del código html generado por el intérprete **Kramdown* añadiéndoles algún valor por medio de atributos.

Para usarlos, añade después del elemento html a modificar tu atributo html válido en formato 'atributo="valor"' dentro de llaves `{ }` y precedidos por dos puntos `:`, **pero siempre después de un carácter comodín de cierre (como `*`, `_`, o `)`), o en una nueva línea (que lo aplicará a todo su elemento precedente)**. Si no el intérprete no sabrá a qué elemento aplicar el atributo.

También se puede utilizar una variable para definir una serie de atributos.

Escribiendo esto

> `Practica con textos [Lorem Ipsum]({{ "/blog/que-es-lorem-ipsum.html" | append: site.baseurl }}){: title="¿Qué es Lorem Ipsum?"} los ejemplos de esta guía básica.`

... tus usuarios ven ...

Practica con textos [Lorem Ipsum]({{ "/blog/que-es-lorem-ipsum.html" | append: site.baseurl }}){: title="¿Qué es Lorem Ipsum?"} los ejemplos de esta guía básica.

... y se programa así

``` html
<p>Practica con textos <a href="/blog/que-es-lorem-ipsum.html" title="¿Qué es Lorem Ipsum?">Lorem Ipsum</a> los ejemplos de esta guía básica.</p>
```

:paperclip:     El atributo global _title_ contiene un texto con información relacionada al elemento al cual pertenece. Los navegadores normalmente muestran este texto en una caja emergente (tip) al pasar el cursor por encima del elemento. Se aplica a enlaces y abreviaturas.

Para los profanos, quizá se vea mejor con estos ejemplos combinados con algunos ejercicios arriba mencionados.

Escribiendo esto

> `Todo este párrafo es rojo.`\\
> `{: style="color: red"}`

... tus usuarios ven ...

Todo este párrafo es rojo.
{: style="color: red"}

... y se programa así

``` html
<p style="color: red">Todo este párrafo es rojo.</p>
```

Escribiendo esto

> `Una lista ordenada con algunos azules`
>
> `1. **Blue**{: style="color: blue"}`\\
> `1. _DarkBlue_{: style="color: darkblue"}`\\
> `1. **BlueViolet**{: style="color: blueviolet"}`\\
> `1. _DodgerBlue_{: style="color: dodgerblue"}`\\
>
> `Mira más colores en [CSS Colors](https://www.w3schools.com/cssref/css_colors.asp){:title="Nombres de color admitidos por todos los navegadores"}`

... tus usuarios ven ...

Una lista ordenada con algunos azules

1. **Blue**{: style="color: blue"}
1. _DarkBlue_{: style="color: darkblue"}
1. **BlueViolet**{: style="color: blueviolet"}
1. _DodgerBlue_{: style="color: dodgerblue"}

Mira más colores en [CSS Colors](https://www.w3schools.com/cssref/css_colors.asp){:title="Nombres de color admitidos por todos los navegadores"}

... y se programa así

<p>Una lista desordenada con otros colores html</p>

``` html
<p>Una lista ordenada con algunos azules</p>

<ol>
  <li><strong style="color: blue">Blue</strong></li>
  <li><em style="color: darkblue">DarkBlue</em></li>
  <li><strong style="color: blueviolet">BlueViolet</strong></li>
  <li><em style="color: dodgerblue">DodgerBlue</em></li>
</ol>

<p>Mira más colores en <a href="https://www.w3schools.com/cssref/css_colors.asp" title="Nombres de color admitidos por todos los navegadores">CSS Colors</a></p>
```



---
