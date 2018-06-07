<!--
.. title: Introducción al Markdown
.. slug: introduccion-al-markdown
.. date: 2018-05-11 22:54:44 UTC
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

Este post está basado en varios posts sobre markdown. La idea es verificar la ejecuci[o
# Introducción

## Filosofía

Markdown pretende ser tan fácil de leer y fácil de escribir como sea posible. La legibilidad, sin embargo, se enfatiza sobre todo lo demás. Un documento con formato de Markdown debe ser publicable tal como está, como texto sin formato, sin que parezca que ha sido marcado con etiquetas o instrucciones de formato. Si bien la sintaxis de Markdown ha sido influenciada por varios filtros existentes de texto a HTML (Setext, atx, Textile, reStructuredText, Grutatext y EtText), la única fuente de inspiración para la sintaxis de Markdown es el formato de correo electrónico de texto sin formato.

## Html en el texto

La sintaxis de Markdown está pensada para un propósito: ser utilizada como un formato para escribir en la web.

Markdown no es un reemplazo para HTML. Su sintaxis es muy pequeña, correspondiendo solo a un subconjunto muy pequeño de etiquetas HTML. La idea no es crear una sintaxis que facilite la inserción de etiquetas HTML, sino facilitar la lectura, la escritura y la edición del texto plano. HTML es un formato de **publicación**; Markdown es un formato de **escritura**. 

Para cualquier necesidad que no esté cubierto por la sintaxis de Markdown, simplemente usa HTML. No hay necesidad de adicionales, s[olo usa las etiquetas HTML correspondientes.

Las únicas restricciones son los elementos HTML a nivel de bloque, por ejemplo, `<div>`, `<table>`, `<pre>`, `<p>`, entre otras, que deben estar separados del contenido circundante por líneas en blanco, y las etiquetas de inicio y fin del bloque no deben indentarse con pestañas o espacios. Markdown es lo suficientemente inteligente como para no agregar etiquetas `<p>` adicionales (no deseadas) alrededor de las etiquetas HTML de nivel de bloque.

Por ejemplo, para agregar una tabla HTML a un artículo de Markdown:

```
Inicio de tabla

<table style="width:100%">
	<tr>
		<th>Nombre</th>
		<th>Apellido</th> 
		<th>Edad</th>
	</tr>
	<tr>
		<td>Sebastian</td>
		<td>Flores</td> 
		<td>35</td>
	</tr>
	<tr>
		<td>Ignacio</td>
		<td>Flores</td> 
		<td>8</td>
	</tr>
</table>

Fin de tabla
```

que se verá así:

Inicio de tabla

<table style="width:100%">
	<tr>
		<th>Nombre</th>
		<th>Apellido</th> 
		<th>Edad</th>
	</tr>
	<tr>
		<td>Sebastian</td>
		<td>Flores</td> 
		<td>35</td>
	</tr>
	<tr>
		<td>Ignacio</td>
		<td>Flores</td> 
		<td>8</td>
	</tr>
</table>

Fin de tabla

Tenga en cuenta que la sintaxis de formato de Markdown no se procesa dentro de las etiquetas HTML de nivel de bloque. Por ejemplo, no puede usar el *énfasis* del estilo de marcado * dentro de un bloque de HTML.

Se pueden mezclar etiquetas HTML, `<span>`, `<cite>`, o `<del>` en cualquier parte de un párrafo de Markdown, elemento de lista o encabezado.

## Escape automático de caracteres especiales

En HTML, hay dos carácteres que tienen un trato especial: `<` y `&`. Los corchetes angulares izquierdos (`<`) se utilizan para iniciar las etiquetas mientras que los ampersands (`&`) se usan para denotar entidades HTML. Si desea mostrarlos como carácteres explícitos debe usarse `&lt;` y `&amp;` que se mostrarán como &lt; y &amp; (como se ven puede depender de la fuente utilizado)

Estos carácteres son problemáticos para lo relacionado con la web. Si se desea escribir sobre AT&amp;T, debe escribir 'AT&amp;T'. 

Incluso se necesita escapar los símbolos dentro de las URL. Por lo tanto, si desea vincular a http://images.google.com/images?num=30&amp;q=larry+bird
necesitas codificar la URL como `http://images.google.com/images?num=30&amp;q=larry+bird`.

# Elementos de span

# Énfasis

Markdown trata los asteriscos (`*`) y los guiones bajos (`_`) como indicadores de énfasis. El texto envuelto con uno `*` o `_` se envolverá con una etiqueta HTML `<em>` double `*`'s o `_`'s se envolverán con una etiqueta HTML `<strong>`. Por ejemplo, `*texto*` y `_texto_`, producira el html `<em>texto</em>` se verá en *itálicas*, mientras que `**negritas**` y `__negritas__` producirá el html `<strong>negritas</strong>` y se verá en **negritas**.

Puedes usar el estilo que prefieras, en lo personal, creo que es mejor usar sólo la convención de asteriscos. La única restricción es que se debe usar el mismo carácter para abrir y cerrar un lapso de énfasis.

No tienen que existir espacios entre el asterisco y las palabras que debe encerrar, por ejemplo `un *increíble* día` aparecerá como "un *increíble* día" mientras que `un * increíble * día` aparecerá como "un * increíble * día".

## Código

Para indicar un código, envuélvalo entre comillas (\`). Por ejemplo, al usar `` `print("Hola Mundo")` `` se vera así: `print("Hola Mundo")`.

Para incluir el carácter \` dentro de un intervalo de código, conviene usar delimitadores de apertura y cierre, además de espacios:

``` `` Hay un backtick literal (`) aquí `` ``` que producirá `` Hay un backtick literal (`) aquí `` 

El texto del código no es interpretado y nunca arrojará errores, por lo que resulta muy conveniente para incluir snippets de código. Se puede indicar una gran función encerrándola entre triple comilla ` ``` `, e incluso en alguno casos, es posible indicar en el inicio del código el lenguaje a ser interpretado. Por ejemplo, el siguiente código:

``````

```python
for i in range(10):
    for j in range(10):
        print(i*j)
```

``````


se verá así

```python
for i in range(10):
    for j in range(10):
        print(i*j)
```

## Links

Para crear un enlace en línea, se utiliza un conjunto de paréntesis regulares y paréntesis redondos: primero el texto que recibirá el enlace.

El texto `[un ejemplo](http://ejemplo.com/ "Título")` produce el código html `<a href="http://ejemplo.com/" title="Title">un ejemplo</a>` y se ve así: 
[un ejemplo](http://ejemplo.com/ "Título"). 

El título es opcional, en efecto, el texto `[otro ejemplo](http://otroejemplo.com/)` produce el código html `<a href="http://otroejemplo.com/">otro ejemplo</a>` que se verá así: [otro ejemplo](http://otroejemplo.com/) 

Si se refiere a un recurso local en el mismo servidor, puede usar rutas relativas: `[Primer post](/posts/primer-post/index.html)` produce el código html `<a href="/posts/primer-post/index.html">otro ejemplo</a>` que quedará como [Primer post](/posts/primer-post/index.html). Se toma como ruta de referencia la ruta en la cual se encuentra el archivo html que llama al enlace.  

## Imágenes

Es difícil idear una sintaxis "natural" para colocar imágenes en un formato de documento de texto plano.

Markdown usa una sintaxis de imagen que se asemeja a la sintaxis de los enlaces.

La sintaxis de la imagen es `![Alt texto](/ruta/a/img.jpg)` o `![Alt text](/path/to/img.jpg "Título opcional")`.

Así, por ejemplo, podemos incrustar imágenes de varias extensiones (gif, jpg, png y svg), con rutas absolutas o locales:

![Alt text](/posts/prueba-de-markdown/colores.gif "Archivo gif") ![Alt text](/posts/prueba-de-markdown/colores.jpg "Archivo jpg") ![Alt text](/posts/prueba-de-markdown/colores.png "Archivo png") ![Alt text](/posts/prueba-de-markdown/colores.svg "Archivo svg")

y sin olvidar un gif animado ![Alt text](/posts/prueba-de-markdown/pbjt.gif "Archivo gif animado")


# Elementos de Bloque

## Párrafos y saltos de línea

Un párrafo es simplemente una o más líneas consecutivas de texto, separadas por una o más líneas en blanco. (Una línea en blanco es cualquier línea que se parece a una línea en blanco; una línea que no contiene más que espacios o pestañas se considera en blanco.) Los párrafos normales no deben sangrarse con espacios o pestañas.

La implicación de la regla de "una o más líneas consecutivas de texto" es que Markdown admite párrafos de texto "envueltos". Esto difiere significativamente de la mayoría de los otros formateadores de texto a HTML (incluida la opción "Convertir saltos de línea" de Movable Type) que traduce cada carácter de salto de línea en un párrafo en una etiqueta <br />.

Cuando quiera insertar una etiqueta de ruptura <br /> usando Markdown, finaliza una línea con dos o más espacios, luego escriba return.

Sí, esto requiere un poco más de esfuerzo para crear un <br />, pero una regla simplista de "cada salto de línea es una <br />" no funcionaría para Markdown. Los elementos de la lista de mapeos en línea y de múltiples párrafos de estilo de correo electrónico de Markdown funcionan mejor, y se ven mejor, cuando los formatea con descansos.

## Encabezados
Markdown admite dos estilos de encabezados, Setext y atx.

Los encabezados de estilo de texto son "subrayados" usando signos iguales (para encabezados de primer nivel) y guiones (para encabezados de segundo nivel). Por ejemplo:
```
Este es un H1
=============

Este es un H2
-------------
```

Cualquier cantidad de subrayado = 's o -'s funcionará.

Los encabezados estilo Atx usan 1-6 caracteres hash al comienzo de la línea, correspondientes a los niveles de encabezado 1-6. Por ejemplo:

```
# Esto es un H1

## Este es un H2

###### Este es un H6
```
Opcionalmente, puede "cerrar" encabezados estilo atx. Esto es puramente cosmético: puede usarlo si cree que se ve mejor. Los hashes de cierre ni siquiera necesitan coincidir con el número de hashes usados ​​para abrir el encabezado. (El número de hashes de apertura determina el nivel del encabezado):

```
# Este es un H1 #

## Esto es un H2 ##

### Este es un H3 ######
```

## Citas

Markdown utiliza caracteres de estilo de correo electrónico para las citas. Si está familiarizado con la cita de pasajes de texto en un mensaje de correo electrónico, entonces sabe cómo crear una blockquote en Markdown. Se ve mejor si ajusta el texto y coloca un> antes de cada línea:

```
> Este es un blockquote con dos párrafos. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla en, laoreet vitae, risus.
>
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
```
Markdown le permite ser flojo y solo colocar el> antes de la primera línea de un párrafo ajustado:

```
> Este es un blockquote con dos párrafos. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla en, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
```

Las comillas en bloque se pueden anidar (es decir, un blockquote-in-a-blockquote) agregando niveles adicionales de>:

```
> Este es el primer nivel de cotización.
>
>> Esto es blockquote anidado.
>
> Volver al primer nivel.
```

Las comillas en bloque pueden contener otros elementos de reducción, incluidos encabezados, listas y bloques de código:

```
> ## Esto es un encabezado.
>
> 1. Este es el primer elemento de la lista.
> 2. Este es el segundo elemento de la lista.
>
> Aquí hay un código de ejemplo:
>
> return shell_exec ("echo $ input | $ markdown_script");
```

Cualquier editor de texto decente debería facilitar las citas de estilo de correo electrónico. Por ejemplo, con BBEdit, puede hacer una selección y elegir Aumentar nivel de presupuesto en el menú Texto.

## Listas

Markdown admite listas ordenadas (numeradas) y desordenadas (con viñetas).

Las listas desordenadas usan asteriscos, más y guiones, de forma intercambiable, como marcadores de lista:

```
* Rojo
* Verde
* Azul
```

es equivalente a:

```
+ Rojo
+ Verde
+ Azul
```

y:

```
- Rojo
- Verde
- Azul
```

Todas ellas se verán así:

* Rojo
* Verde
* Azul


Las listas ordenadas usan números seguidos de puntos:

```
1. Primer ítem
2. Segundo ítem
3. Tercer ítem
```

Es importante tener en cuenta que los números reales que utiliza para marcar la lista no tienen ningún efecto en la salida HTML que Markdown produce. El Markdown HTML producido a partir de la lista anterior es:

```
<ol>
<li> Primer ítem </li>
<li> Segundo ítem </li>
<li> Tercer ítem </li>
</ol>
```

Si en su lugar escribió la lista en Markdown de esta manera:

```
1. Primer ítem
1. Segundo ítem
1. Tercer ítem
```

o incluso:

```
3. Primer ítem
2. Segundo ítem
42. Tercer ítem
```

obtendrías la misma salida de HTML, y se verá así:

2. Primer ítem
1. Segundo ítem
1. Tercer ítem

```
Los marcadores de lista generalmente comienzan en el margen izquierdo, pero pueden tener sangría de hasta tres espacios. Los marcadores de lista deben ir seguidos de uno o más espacios o una pestaña.

Para que las listas se vean bien, puede ajustar elementos con sangrías colgantes:

* Lorem ipsum dolor sit amet, Consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla en, laoreet vitae, risus.
* Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.
Pero si quieres ser flojo, no tienes que:

* Lorem ipsum dolor sit amet, Consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla en, laoreet vitae, risus.
* Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.
Si los elementos de la lista están separados por líneas en blanco, Markdown ajustará los elementos en etiquetas <p> en la salida HTML. Por ejemplo, esta entrada:

* Ave
* Magia
se convertirá en:

<ul>
<li> Pájaro </ li>
<li> Magia </ li>
</ ul>
Pero esto:

* Ave

* Magia
se convertirá en:

<ul>
<li> <p> Bird </ p> </ li>
<li> <p> Magia </ p> </ li>
</ ul>
Los artículos de la lista pueden consistir en varios párrafos. Cada párrafo posterior en un elemento de la lista debe sangrarse con 4 espacios o una sola pestaña:

1. Este es un elemento de la lista con dos párrafos. Lorem ipsum dolor
    sentarse amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla en, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sentarse amet velit.

2. Suspendisse id sem consectetuer libero luctus adipiscing.
Se ve bien si sangras cada línea de los párrafos siguientes, pero una vez más, Markdown te permitirá ser flojo:

* Este es un elemento de la lista con dos párrafos.

    Este es el segundo párrafo en el elemento de la lista. Eres
solo se requiere para sangrar la primera línea. Lorem ipsum dolor
sentarse amet, consectetuer adipiscing elit.

* Otro elemento en la misma lista.
Para poner una blockquote dentro de un elemento de lista, los delimitadores de blockquote necesitan ser sangrados:

* Un elemento de lista con una blockquote:

    > Esto es un blockquote
    > dentro de un elemento de la lista.
Para poner un bloque de código dentro de un elemento de lista, el bloque de código debe sangrarse dos veces: 8 espacios o dos pestañas:

* Un elemento de lista con un bloque de código:

        <el código va aquí>
Vale la pena señalar que es posible activar una lista ordenada por accidente, escribiendo algo como esto:

1986. Qué gran temporada.
En otras palabras, una secuencia de número-período-espacio al comienzo de una línea. Para evitar esto, puede hacer una barra invertida, escapar del punto:

1986 \. Que gran temporada.
Información del Traductor de GoogleComunidadMóvilAcerca de GooglePrivacidad y condicionesAyudaDanos tu opinión
```

## Bloques de código

Los bloques de código preformateados se utilizan para escribir sobre programación o código fuente de marcado. En lugar de formar párrafos normales, las líneas de un bloque de código se toman literalmente (no se intepretan). Markdown coloca un bloque de código en las etiquetas `<pre>` y `<code>`. La sintaxis regular de Markdown no se procesa dentro de los bloques de código. Por ejemplo, los asteriscos son solo asteriscos literales dentro de un bloque de código. Esto significa que también es fácil usar Markdown para escribir sobre la propia sintaxis de Markdown.

Para producir un bloque de código en Markdown, simplemente indenta cada línea del bloque por al menos 4 espacios o 1 tabulación. Un nivel de indentación (4 espacios o 1 tabulación) se elimina de cada línea del bloque de código. Por ejemplo:

```
Ejemplo de código:

    for i in range(10):
        for j in range(10):
            print(i*j)
```

se convertirá en:

```
<p>Ejemplo de código:</p>

<pre> <code>
for i in range(10):
    for j in range(10):
        print(i*j)
</ code> </ pre>
```

y se mostrará así:

Ejemplo de código:

    for i in range(10):
        for j in range(10):
            print(i*j)


Un bloque de código continúa hasta que llega a una línea que no está sangrada (o al final del artículo).

Dentro de un bloque de código, ampersands (&amp;) y corchetes angulares (&lt; y &wt;) se convierten automáticamente en código HTML. Esto hace que sea muy fácil incluir un código de ejemplo usando Markdown; simplemente péguelo e indente, y Markdown manejará la molestia de codificar los símbolos y los corchetes angulares. 


# Reglas horizontales

Es posible generar una regla horizontal (`<hr/>`) colocando tres o más guiones, asteriscos o guiones bajos en una línea por sí solos. Si lo desea, puede usar espacios entre los guiones o los asteriscos. Cada una de las siguientes líneas producirá una regla horizontal:
```
* * *
***
*****
- - -
---------------------------------------
```
y se vera asi

***



# Temas avanzados

## Enlaces automáticos

Markdown admite enlaces "automáticos" para URL y direcciones de correo electrónico: utilizando corchetes angulares para la URL o la dirección de correo electrónico. 
Markdown convertirá `<http://example.com/>` en `<a href="http://example.com/"> http://example.com/</a>`, por ejemplo, asi <http://example.com/>. 
Los enlaces automáticos para direcciones de correo electrónico funcionan de manera similar, excepto que se realizará un poco de codificación para ayudar a ocultar su dirección de spambots de recolección de direcciones. Por ejemplo, Markdown cambiará `<dirección@ejemplo.com>` en algo como `<a href="&#x6D;&#x61;i&#x6C;&#x74;&#x6F;:&#x61;&#x64;&#x64;&#x72;&#x65;&#115;&#115;&#64;&#101;&#120;&#x61;&#109;&#x70;&#x6C;e&#x2E;&#99;&#111; &#109;">&#x61;&#x64;&#x64;&#x72;&#x65;&#115;&#115;&#64;&#101;&#120;&#x61;&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;&#109;</a>` pero que se verá y funcionará correctamente en el navegador.

Este tipo de truco de codificación de entidades engañará a muchos, si no a la mayoría, de los bots de recolección de direcciones, pero definitivamente no los engañará a todos. Es mejor que nada, pero una dirección publicada de esta manera probablemente comenzará a recibir correo no deseado.

## Carácteres especiales

Markdown le permite usar `\` (barra invertida) para generar caracteres literales que de otro modo tendrían un significado especial en la sintaxis de formato de Markdown. Por ejemplo, si desea rodear una palabra con asteriscos literales (`*`) en lugar de que ponerle negritas, se debe usar `\*asteriscos literales\*` para lograr \*asteriscos literales\* en lugar de *asteriscos literales*.

Markdown proporciona escapes de barra invertida para los siguientes caracteres:

```
\ backslash
`retroceso
* asterisco
_ guion bajo
{} llaves
[] corchetes
() paréntesis
# símbolo de almohadilla
+ signo más
- signo menos (guion)
. punto
! signo de exclamación
```

# Links - avanzados
Los enlaces de estilo de referencia usan un segundo conjunto de corchetes, dentro del cual coloca una etiqueta de su elección para identificar el enlace:

Este es un enlace de estilo de referencia [un ejemplo] [id].
Opcionalmente puede usar un espacio para separar los conjuntos de corchetes:

Este es un enlace de estilo de referencia [un ejemplo] [id].
Luego, en cualquier parte del documento, defina su etiqueta de enlace de esta manera, en una línea sola:

[id]: http://example.com/ "Título opcional aquí"
Es decir:

Corchetes que contienen el identificador de enlace (opcionalmente sangría desde el margen izquierdo utilizando hasta tres espacios);
seguido por dos puntos;
seguido de uno o más espacios (o pestañas);
seguido de la URL del enlace;
opcionalmente seguido por un atributo de título para el enlace, encerrado en comillas dobles o simples, o encerrado entre paréntesis.
Las siguientes tres definiciones de enlace son equivalentes:

[foo]: http://example.com/ "Título opcional aquí"
[foo]: http://example.com/ 'Título opcional aquí'
[foo]: http://example.com/ (Título opcional aquí)
NOTA: Existe un error conocido en Markdown.pl 1.0.1 que impide que se utilicen comillas simples para delimitar títulos de enlaces.

La URL del enlace puede, opcionalmente, estar rodeada por corchetes angulares:

[id]: <http://example.com/> "Título opcional aquí"
Puede poner el atributo de título en la línea siguiente y usar espacios o pestañas adicionales para el relleno, que tiende a verse mejor con URL más largas:

[id]: http://example.com/longish/path/to/resource/here
    "Título opcional aquí"
Las definiciones de enlace solo se usan para crear enlaces durante el procesamiento de Markdown, y se eliminan de su documento en el resultado HTML.

Los nombres de definición de enlace pueden consistir en letras, números, espacios y signos de puntuación, pero no distinguen entre mayúsculas y minúsculas. P.ej. estos dos enlaces:

[enlace de texto] [a]
[enlace de texto] [A]
son equivalentes.

El acceso directo de nombre de enlace implícito le permite omitir el nombre del enlace, en cuyo caso el texto del enlace se utiliza como el nombre. Simplemente use un conjunto vacío de corchetes, por ejemplo, para vincular la palabra "Google" al sitio web google.com, simplemente escriba:

[Google] []
Y luego define el enlace:

[Google]: http://google.com/
Como los nombres de los enlaces pueden contener espacios, este atajo incluso funciona para varias palabras en el texto del enlace:

Visita [Daring Fireball] [] para más información.
Y luego define el enlace:

[Daring Fireball]: http://daringfireball.net/
Las definiciones de enlaces pueden colocarse en cualquier parte de su documento de reducción. Tiendo a ponerlos inmediatamente después de cada párrafo en el que se usan, pero si lo desea, puede ponerlos todos al final de su documento, como notas a pie de página.

Aquí hay un ejemplo de enlaces de referencia en acción:

Recibo 10 veces más tráfico de [Google] [1] que de
[Yahoo] [2] o [MSN] [3].

  [1]: http://google.com/ "Google"
  [2]: http://search.yahoo.com/ "Búsqueda de Yahoo"
  [3]: http://search.msn.com/ "Búsqueda de MSN"
Usando el atajo de nombre de enlace implícito, en su lugar podría escribir:

Recibo 10 veces más tráfico de [Google] [] que de
[Yahoo] [] o [MSN] [].

  [google]: http://google.com/ "Google"
  [yahoo]: http://search.yahoo.com/ "Búsqueda de Yahoo"
  [msn]: http://search.msn.com/ "Búsqueda de MSN"
Los dos ejemplos anteriores producirán el siguiente resultado HTML:

<p> Recibo 10 veces más tráfico de <a href = "http://google.com/"
title = "Google"> Google </a> que desde
<a href="http://search.yahoo.com/" title="Yahoo Search"> Yahoo </a>
o <a href="http://search.msn.com/" title="MSN Search"> MSN </a>. </ p>
A modo de comparación, aquí está el mismo párrafo escrito usando el estilo de enlace en línea de Markdown:

Recibo 10 veces más tráfico de [Google] (http://google.com/ "Google")
que desde [Yahoo] (http://search.yahoo.com/ "Yahoo Search") o
[MSN] (http://search.msn.com/ "Búsqueda de MSN").
El punto de referencia de los enlaces de estilo no es que sean más fáciles de escribir. El punto es que con los enlaces de estilo de referencia, la fuente de su documento es mucho más legible. Compare los ejemplos anteriores: al usar enlaces de estilo de referencia, el párrafo en sí tiene una longitud de solo 81 caracteres; con enlaces en línea, tiene 176 caracteres; y como HTML sin formato, tiene 234 caracteres. En el HTML sin procesar, hay más marcado que texto.

Con los enlaces de estilo de referencia de Markdown, un documento de origen se asemeja mucho más al resultado final, tal como se representa en un navegador. Al permitirle mover los metadatos relacionados con el marcado hacia afuera del párrafo, puede agregar enlaces sin interrumpir el flujo narrativo de su prosa.


# Imágenes - avanzados



Es decir:

Un signo de exclamación:!
seguido de un conjunto de corchetes, que contiene el texto del atributo alt para la imagen;
seguido de un conjunto de paréntesis, que contiene la URL o la ruta a la imagen, y un atributo de título opcional encerrado en comillas dobles o simples.
La sintaxis de la imagen del estilo de referencia se ve así:

! [Alt text] [id]
Donde "id" es el nombre de una referencia de imagen definida. Las referencias de imagen se definen usando una sintaxis idéntica a las referencias de enlace:

[id]: url / to / image "atributo de título opcional"
Al escribir estas líneas, Markdown no tiene sintaxis para especificar las dimensiones de una imagen; si esto es importante para usted, simplemente puede usar etiquetas HTML <img> normales.
