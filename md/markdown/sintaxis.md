# Sintaxis básica

Como hemos dicho, Markdown se basa en ficheros de tipos texto, que no contienen ninguna información interna sobre el formato. Esta información, se especificará de forma explícita mediante hashtags, que serán visibles en todo momento, y que facilitarán, por un lado, su interpretación en la hora de exportarlos a otro formato, pero también su lectura por parte de las personas.

En este apartado, vamos a ver cuáles son los diferentes elementos que podemos utilizar en un texto en formato Markdown, así como las principales marcas de formato.

## 1. Párrafos

Un párrafo, tal y como lo entiende Markdown, es un bloque de texto definido entre dos saltos de línea (tecla `Intro/Entero/Entrar`). 

Si utilizamos solo un salto de línea, se sobreentiende que es el mismo párrafo, y en la hora de generar el documento, lo veremos como tal.

```markdown title="Markdown" linenums="1"
Este es el primer párrafo, como veis, necesita dos saltos de línea, o el que sería el mismo, una línea en blanco después del párrafo.

Este es otro párrafo.
```

!!! note "Resultado"
    Este es el primer párrafo, como veis, necesita dos saltos de línea, o el que sería el mismo, una línea en blanco después del párrafo.

    Este es otro párrafo.

## 2. Cabeceras

Hay varias formas de marcar cabeceras, nosotros utilizaremos el Estilo ATX, al cual, utilizamos el símbolo (`#`) antes del texto para indicar el nivel de la cabecera. Se admiten hasta seis niveles de profundidad (`######`), el que vendría a ser del (`h1`) hasta el (`h6`) de #HTML.

```markdown title="Markdown" linenums="1"
# Encabezado 1

## Encabezado 2

### Encabezado 3

...
```
>
> A tener con cuenta
>
> La versión estándar de Markdown no requiere de una línea en blanco antes de una cabecera, pero otras versiones, como por ejemplo la de *Pandoc* sí que la requiere. Sin embargo, aunque el estándar no lo utilizo, conviene añadirla puesto que facilita así la lectura y localización de estas.
>
> Algunas implementaciones, tampoco requieren de un espacio entre el símbolo `#` inicial y el primer carácter del título.
>

### 2.1. Atributos a la cabecera

Cuando se genera un documento, ya sea PDF, #HTML u otro formato a partir de un documento en Markdown, a las cabeceras se los asigna un identificador de manera automática, para que se pueda hacer referencia a ellas desde otras partes del documento. Este identificador se obtiene a partir del texto de la cabecera, por el que si esta es larga, el identificador también lo será. La versión de Pandoc, nos permite añadir ciertos atributos a las cabeceras, entre las que se encuentra el identificador. 

Dada, por ejemplo, una cabecera como la siguiente:

```markdown title="Markdown" linenums="1"
# Introducción: El arte de escribir ante un ordenador
```
El identificador que se genera es: `id="introducción-lart-describir-ante-un-ordenador"`. 

Esta cabecera, la podríamos haber escrito también de la siguiente forma:

```markdown title="Markdown" linenums="1"
# Introducción: El arte de escribir ante un ordenador { #introduccio }
```

Siente el identificador de la cabecera solo `#introduccio`, de forma que podemos hacer referencia al apartado mediante este.

## 3. Formato de texto

Markdown nos permite hacer uso del símbolo del asterisco como marca de formato de la siguiente forma:

- Negrita: rodea el texto con `**`.
- Cursiva: rodea el texto con `*`.
- Negrita y cursiva: Usa tres asteriscos.

Hay que tener en cuenta que no tenemos que añadir ningún espacio entre los asteriscos del principio y la primera palabra y los asteriscos del final y la última.

```markdown title="Markdown" linenums="1"
**Texto en negrita**
*Texto en cursiva*
***Texto en negrita y cursiva***

Si añadimos algún espacio entre medio, ** no se interpretará correctamente **
```
!!! note "Resultado"
    **Texto en negrita**

    *Texto en cursiva*
    
    ***Texto en negrita y cursiva***

    Si añadimos algún espacio entre medio, ** no se interpretará correctamente **


## 4. Líneas horizontales

Una línea horizontal se define mediante tres o más símbolos `-` o `_`, separados o no por espacios:

```markdown title="Markdown" linenums="1"
- - -

o 

_ _ _
```

!!! note "Resultado"

    - - -

    o 

    _ _ _


## 5. Listas

Markdown permite hacer uso tanto de listas ordenadas como listas no ordenadas.

#### 5.1. Listas no ordenadas

Las listas no ordenadas se marcan haciendo uso de los símbolos `*`, `+` o `-` a primeros de cada elemento, e incluyendo cada ítem en una línea diferente (y no hacen falta dos saltos de línea).

```markdown title="Markdown" linenums="1"
* Elemento 1
* Elemento 2
...
```

Cada elemento de la lista puede contener varios párrafos, y otros contenidos a nivel de bloque. Cuando queremos incluir varios párrafos en un ítem de la lista, el segundo párrafo y posterior tendrán que ir precedidos por una línea en blanco, y sangrados para alinearse con el contenido que no sea el espacio después del marcador de la lista.

Por ejemplo:

```markdown title="Markdown" linenums="1"
* Primer elemento de la lista
* Segundo elemento de la lista

  Otro párrafo correspondiente al segundo elemento de la lista.
  No hace falta un espacio en blanco entre el último párrafo y el siguiente elemento,
  pero lo podemos añadir para facilitar la lectura de la lista.

* Tercer elemento de la lista.
```

Para generar listas anidadas dentro de otras, simplemente tendrás que añadir cuatro espacios en blanco antes del siguiente `*`,`-` o `+`.

```markdown title="Markdown" linenums="1"
* Elemento 1
    * subelemento 1.1
        * subelemento 1.1.1
        * subelemento 1.1.2
    * subelemento 1.2
    * subelemento 1.3
* Elemento 2
```

En estos casos, como que podemos utilizar varios símbolos para indicar listas, se suele utilizar un elemento por cada nivel de la lista, con el fin de facilitar la lectura del texto plano:

```markdown title="Markdown" linenums="1"
* Elemento 1
    + subelemento 1.1
        - subelemento 1.1.1
        - subelemento 1.1.2
    + subelemento 1.2
    + subelemento 1.3
* Elemento 2
```

!!! note "Resultado"
    * Elemento 1
        + subelemento 1.1
            - subelemento 1.1.1
            - subelemento 1.1.2
        + subelemento 1.2
        + subelemento 1.3
    * Elemento 2


#### 5.2. Listas ordenadas

El funcionamiento de las listas ordenadas es el mismo que las no ordenadas, salvo que cada elemento de la lista lleva un número.

En la versión estándar de Markdown, los elementos que indican la orden tienen que ser números seguidos de un punto y un espacio. En el estándar, estos números se ignoran, por lo que la lista:

```markdown title="Markdown" linenums="1"
1. Elemento 1
2. Elemento 2
3. Elemento 3
```

Será la misma que:

```markdown title="Markdown" linenums="1"
4. Elemento 1
5. Elemento 2
6. Elemento 3
```
!!! note "Resultado"
    4. Elemento 1
    5. Elemento 2
    6. Elemento 3

## 6. Tablas

Las tablas nos sirven para presentar información de manera organizada.

La versión original de Markdown de John Gruber no incluye la definición de tablas en la sintaxis de Markdown. Como que inicialmente se creó como una herramienta para hacer la conversión a HTML, para añadir tablas se utilizaba directamente este lenguaje.

Sin embargo, las diferentes variantes de Markdown han ido añadiendo notaciones y extensiones al Markdown original para soportar tablas.

La sintaxis para crear tablas del Markdown de Github es una de las más extendidas, y hace uso de barras verticales (`|`) y guiones (`-`) para crearlas. Los guiones se utilizan para crear el encabezamiento de cada columna, y las barras verticales sirven de separador de cada columna. Además, para que la tabla se represente correctamente, hace falta una línea en blanco antes de la tabla.

Las tablas, en este formato, tienen que tener necesariamente una cabecera y un cuerpo, y seguirán la siguiente sintaxis:

```markdown title="Markdown" linenums="1"
| Cabecera 1 | Cabecera 2 |
|-------------|-------------|
| Valor 1     | Valor 2     |
| Valor 3     | Valor 4     |
```
!!! note "Resultado"

     Cabecera 1 | Cabecera 2 
    -------------|-------------
     Valor 1     | Valor 2     
     Valor 3     | Valor 4    

  
Algunas consideraciones:

* Podemos añadir tantos campos (columnas) como queramos. 
* La línea que separa la cabecera del cuerpo `|---|---|` es obligatoria, pero no es necesario que tenga tantos caracteres como tengan las cabeceras, por el que no hace falta que la tabla esté completamente alineada. 
* Las barras verticales (`|`) del principio y del final son opcionales.

#### 6.1. Formateado el contenido de una tabla

Dentro de una tabla podemos utilizar también ciertas marcas de formato, como negritas, cursivas, enlaces, imágenes...

Además, podemos alinear el texto a la izquierda, a la derecha o en el centro de la columna, añadiendo la marca dos puntos `:`, al lado izquierdo, derecho, o a los dos, de los guiones del encabezamiento.

Vemos-lo con un ejemplo. La siguiente definición de tabla:

```markdown title="Markdown" linenums="1"
| Texto a la izquierda | Texto centrado | Texto a la derecha |
|        :---       |     :---:    |      ---:       |
| xxx               | xxx          | xxx             |
| xxxxx             | xxxxx        | xxxxx           |
```

!!! note "Resultado"

    | Texto a la izquierda | Texto centrado | Texto a la derecha |
    |        :---       |     :---:    |      ---:       |
    | xxx               | xxx          | xxx             |
    | xxxxx             | xxxxx        | xxxxx           |

>
> Si queremos añadir dentro de una tabla una barra vertical (|) como contenido, tenemos que poner antes el símbolo (`\`), para indicar que el carácter siguiente no se tiene que interpretar como marca de formato Markdown. Esta barra invertida se denomina carácter de escape*, y a la combinación de ella con cualquier marca que queramos que no se interprete se conoce como secuencia de escape*.
>

## 7. Fragmentos de código

Markdown tiene un amplio uso en la documentación técnica de proyectos informáticos, donde es habitual incluir fragmentos del código fuente de los programas. Para resaltar estos tipos de fragmentos, Markdown utiliza una sintaxis especial, haciendo uso de los caracteres del acento abierto: \`.

Cuando se trata de fragmentos de código que tienen que ir en la misma línea que el texto, por ejemplo si queremos indicar un hashtag #HTML, lo hacemos, \`de este modo\`, haciendo uso de un único carácter de acento, mientras que si el que volamos es escribir un bloque de código, utilizaríamos tres símbolos de acento abierto \`\`\`. Además, detrás los primeros símbolos, podemos especificar de qué lenguaje se trata. Por ejemplo, para indicar el código #HTML de una página web, haríamos:

```markdown title="Markdown" linenums="1"
    ```html title="HTML" linenums="1" 
        <html>
            <body>
            <h1>Título de la página web</h1>
            <p>Párrafo</p>
            </body>
        </html>
    ```
```

Hay que remarcar que el nombre del lenguaje detrás las comillas hace que al mostrar el resultado, se tenga en cuenta el lenguaje de programación para resaltar la sintaxis propia del lenguaje.

## 8. Citas

En Markdown, un bloque de texto en forma de cita consiste en uno o más párrafos u otros elementos de bloque (como, por ejemplo, listas o cabeceras), donde cada línea se encuentra precediera del carácter `>` y opcionalmente un espacio.

Vemos algunos ejemplos:

Ejemplo:

```markdown title="Markdown" linenums="1" 
>
> Un documento con formato Markdown tendría que ser publicable tal cual, como texto plano, sin que parezco que se ha marcado con hashtags o instrucciones de formato.
>
> John Gruber
```

!!! note "Resultado"
    >
    > Un documento con formato Markdown tendría que ser publicable tal cual, como texto plano, sin que parezco que se ha marcado con hashtags o instrucciones de formato.
    >
    > John Gruber

## 9. Enlaces

Markdown nos permite generar enlaces tanto a direcciones de Internet, como hacer referencia a ficheros locales, mediante su ruta relativa o incluso dentro del propio documento.

El formato general para añadir un enlace es el siguiente:

```markdown title="Markdown" linenums="1"
[Texto del enlace](#URL_o_dirección_relativa)
```

Por ejemplo, para añadir un enlace a un sitio web, escribiremos:

```markdown title="Markdown" linenums="1"
Ir a la web del [IES Dr. Lluís Simarro](https://portal.edu.gva.es/ieslluissimarro/)
```

!!! note "Resultado"
     Ir a la web del [IES Dr. Lluís Simarro](https://portal.edu.gva.es/ieslluissimarro/)

### 9.1. Enlaces internos

Para añadir un enlace a una sección de nuestro documento, haremos uso del identificador que se asigna automáticamente, o bien que le hemos asignado nosotros. 

Por ejemplo, si para el apartado introductorio añadimos un identificador de la siguiente forma:

```markdown title="Markdown" linenums="1"
# Introducción: El arte de escribir ante un ordenador {#introduccion}
```

Podemos hacer referencia a él de la manera siguiente:

```markdown title="Markdown" linenums="1"
Haz clic [en el siguiente enlace](#introduccion) para volver a la sección de Introducción.
```

!!! note "Resultado"
    Haz clic [en el siguiente enlace](#introduccion) para volver a la sección de Introducción.


## 10. Imágenes

La sintaxis para añadir una imagen es parecida a la del enlace, precedida de una exclamación `!`:

```markdown title="Markdown" linenums="1"
![Texto alternativo o pie de la imagen](Ubicación de la imagen)
```

Al igual que los enlaces, la ubicación puede ser una dirección de Internet o bien la ruta a un fichero local a nuestro ordenador:

```markdown title="Markdown" linenums="1"
![Logotipo de Markdown a la Wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/markdown-mark.svg/1920px-markdown-mark.svg.png)

![Logotipo de Markdown a en una ruta relativa](./../img/logoMarkdown.png)
```

En este segundo caso, busca la imagen *logoMarkdown.png* en una carpeta imágenes ubicada en la carpeta indicada.

Hay que tener en cuenta que cuando se exporte el fichero a HTML, estas referencias seguirán existiendo al código HTML.

#### 10.1. Añadiendo tamaño a las imágenes

Algunas versiones de Markdown (como Pandoc) permiten añadir ciertos atributos a las imágenes. 
Entre estos destacan especialmente (`width`) y (`height`), que permiten especificar el tamaño de la imagen. 

Si no se indica nada, el tamaño se entiende que se especifica en píxeles, pero podemos utilizar otras unidades como *px, #cm, mm, in, inch y %*, sin incluir espacios entre el número y las unidades. 

Ejemplos:

```markdown title="Markdown" linenums="1"
![Imagen 1 - 10cm](./../img/logoMarkdown.png){ width=10cm }

![Imagen 2 - 50mm](./../img/logoMarkdown.png){ width=50mm }

![Imagen 3 - 50%](./../img/logoMarkdown.png){ width=50% }
```
!!! note "Resultado"

    ![Imagen 1 - 10cm](./../img/logoMarkdown.png){ width=10cm }

    ![Imagen 2 - 50mm](./../img/logoMarkdown.png){ width=50mm }

    ![Imagen 3 - 50%](./../img/logoMarkdown.png){ width=50% }