# **LAYOUTS - FLOATS - FLEXBOX AND CSS GRID FUNDAMENTALS**

## LAYOUTS

- "LAYOUTS" es la forma en que el texto, las imágenes y otro conenido se coloca y organiza en una página web

- le da a la página una estructura visual en donde colocamos nuestro contenido

- Crear un Layout: organizar los elementos de la página en una estructura visual, en lugar de simplemente tener uno despues de otro (flujo normal)

- DOS TIPOS DE DISEÑO:

  - Diseño de página: disposicion de los elementos dentro de una pagina web
  - Diseño de componentes: cada bloque que compone la pagina web o sitio web. Cada componente tiene un diseño en particular y el contenido de cada componente tiene piezas mas pequeñas con un diseño particular

- TÉCNICAS DE CREACION DE LAYOUTS EN CSS

  - Floats: antigua forma de construir layouts de todos los tamaños usando la propiedad FLOAT de CSS.
  - Flex: forma moderna de diseñar layouts. Perfecto para construir diseños unidimensionales, basicamente es solo una fila y sin usar floats. Perfecto para diseñar componentes mas simples
  - Grid: crear layouts bidimensionales. Perfecto para layouts grandes y complejos

- Los elementos con float salen del flujo normal y tienen un impacto en los elementos circundantes. Textos y elementos en linea rodean a los elementos que flotan. El elemento contenedor no ajusta su altura al elemento flotante que contiene, colapsando la misma.

  - Solución:

    - En el contenedor padre de los elementos flotantes, en el HTML, agregar `class="clearfix"`
    - En CSS

      ```css
      .clearfix::after {
        clear: both; /*por tener float en ambas direcciones*/
        content: "";
        display: block; /*los pseudoelementos son in-line*/
      }
      ```

- Hacer que un elemento del HTML no siga el orden de los floats, envolviendo a los elementos que flotan, en CSS agregar al selector del elemento `clear: both`

# **FLEXBOX**

- El contenedor padre de los elementos que van a ser flexibles se le aplica `display: flex;`
- HORIZONTAL: Los elementos flexibles se acomodan uno al lado de otro de izquierda a derecha ocupando el espacio necesario a su contenido y son tan altos como el elemento mas alto, si no hay un alto definido, el alto es igual al que necesita segun su contenido
- `align-items` -> estando con un flex-direction: row (horizontal) permite acomodar los elementos flotantes de manera vertical dentro de su contenedor. El contenedor flexible toma la altura del elemento mas alto pero todos los demas toman el espacio necesario para su contenido (si no tienen especificado un alto)

## QUE ES FLEXBOX?

- Flexbox es un conjunto de propiedades de CSS para construir layouts unidimensionales
- Hace que sea facil alinear elementos automaticamente entre si dentro de un determinado contenedor principal, tanto horizontalmete como verticalmente
- Resuelve problemas comunes como el centrado vertical y tambien creando columnas de igual altura

## TERMINOS IMPORTANTES

- FLEX CONTAINER: el elemento en el que queremos usar flexbox
- Establecer `display: flex;` y todos los elementos del contenedor se convertiran en FLEX ITEMS
- MAIN AXIS: la direccion en la que se colocan los elementos flexibles, es el eje principal en el que queremos colocar los elementos
- CROSS AXIS: eje transversal al main axis, es el eje secundario

## ELEMENTOS IMPORTANTES DE FLEX

- `gap: 0(valor por defecto) | <lenght>` -> crea ESPACIO ENTRE LOS ELEMENTOS sin usar margin (al inspeccionar los elementos no presentan margenes en la separacion entre los mismos)

- `justify-content: flex-start(valor por defecto) | flex-end | center | space-between | space-around | space-evenly` -> alinea los elementos a lo largo del que sea nuestro MAIN AXIS (horizontal por default pero si trabajamos verticalmente pasa a ser nuestro eje principal)

- `align-items: stretch(valor por defecto) | flex-start | flex-end | center | baseline` -> alinea los elementos a lo largo del CROSS AXIS (vertical por defecto, pero si trabajamos verticalmente pasa a ser horizontal el eje secundario)

- `flex-direction: row(valor por defecto) | row-reverse | column | column-reverse` -> define cual va a ser el MAIN AXIS

- `flex-wrap: nowrap(valor por defecto) | wrap | wrap-reverse` -> si los elementos son muy largos los envuelve en una nueva linea

- `align-content: stretch(valor por defecto) | flex-start | flex-end | center | space-between | space-around`-> solo se aplica cuando hay multiples lineas (flex-wrap: wrap)

## PROPIEDADES DE LOS ELEMENTOS FLEXIBLES

- `align-self: auto(valor por defecto) | stretch | flex-start | flex-end | center | baseline` -> sobreescribe la propiedad align-items para elementos flexibles individuales

- `flex-grow: 0(valor por defecto) | <interger>` -> para permitir que un elemento crezca(0 significa no, 1+ significa si)

- `flex-shrink: 1(valor por defecto) | <interger>` -> para permitir que un elemento se encoja (0 significa no, 1+ significa si)

- `flex-basis: auto(valor por defecto) | <lenght>` -> para permitir el ancho de un elemento, en lugar de la propiedad width

- `flex: 0 1 auto(valor por defecto) | <int> <int> <int>` -> shorthand recomendado para flex-grow flex-shrink flex-basis

- `order: 0 | <interger>` -> para cambiar el orden de los elementos flexibles visualmente en la página sin cambiar el orden en el codigo fuente

  - Todos los elementos flexibles tiene el valor 0, para llevar cualquiera de ellos al inicio se le debe dar un numero menor a 0
    Para llevar un elemento al final hay que darle un valor mayor a 0
    Se usa principalmente para acomodar los elementos desde un dispositvo mas grande a uno mas pequeño

  - FLEX-BASIS no es rigido, algunos elementos no respetan el ancho otorgado en la propiedad, esta es una recomendacion al navegador, pero éste averigua la longitud óptima en relacion al contenido del elemento flexible.

  - FLEX-SHRINK: establecer flex-shrink: 1; flexbox de forma predeterminada permite encoger los elementos para que quepen en el contenedor si no hay espacio suficiente, adapta los elementos a un tamaño que les permita quepar en el contenedor a pesar de haberles fijado un ancho. Establecer flex-shrink: 0 hace que los elementos no se enconjan para quepar, sino que les otorga el ancho que se establecio en flex-basis desbordando del contenedor
    (cuando los elementos se desbordan del contenedor)

  - FLEX-GROW: determina si se le permite a los elementos crecer tanto como puedan o no para rellenar el contenedor o no.
    flex-grow: 0; no crecen los elementos hasta completar el contenedor y se adaptan a su contenido o al valor que se le otorgue con flex-basis (en caso que el contenido es menor al valor ancho otorgado)
    flex-grow: 1; los elementos crecen en igual tamaño hasta completar el contenedor
    (cuando los elementos les sobra espacio en el contenedor)

  - FLEX-BASIS, FLEX-SHRINK Y FLEX-GROW se aplican a los elementos flexibles, sea a todos los del contenedor, a algunos o a uno

  - Si un elemento flexible tiene un flex-grow > 1, ese elemento crece en la proporcion de su numero, si tiene un 2 toma el doble del espacio disponible que los demas elementos

  - FLEX es un shorthand de flex-grow flex-shrink flex-basis
    flex: 1 -> reparte el espacio disponible de igual manera entre todos los elementos flexibles y crecen hasta completar el espacio disponible del contenedor

## [CHALLENGE #3 FLEXBOX](https://codepen.io/PatriciaVendrame/pen/yLoeQMe)

# CSS GRID

En CSS GRID existe GRID CONTAINER y GRID ITEMS

- `display: grid` -> en el contenedor para habilitar css grid y luego especificar las columnas y las filas
- `grid-template-column: <valor>` -> definir tantos valores de ancho como queramos y para cada uno de estos valores se creara una columna. Si no se especifican las filas, se crearan tantas como sea necesario para adaptar el contenido. Los elementos de una fila se acomodan al mayor tamaño de los elementos, caso contrario toman la altura del contenido
- `grid-template-rows: <valor>` -> tantas filas como valores se agreguen, los elementos que tiene un alto establecido respetan ese alto, los demas elementos se estiran hasta completar el alto de la fila
- `gap: <valor>`es la unica manera de especificar espacios entre los elementos de la grilla, usar siempre el espacio y no los margenes. Gap agrega espacio entre los elementos en columnas y filas
- `column-gap: <valor>` -> agrega espacio entre las columnas, independiente del espacio de las filas
- `row-gap: <valor>` -> agrega espacio entre las filas, independiente del espacio de las columnas

## QUE ES CSS GRID?

- CSS GRID es un conjunto de propiedades para construir layouts bidimensionales
- Se puede dividir un elemento contenedor en filas y columnas y luego llenar con elementos secundarios
- Permite escribir menos HTML anidado y también más fácil de leer CSS
- CSS GRID no reemplaza a FLEXBOX, al contrario, trabajan perfectamente juntos. Si se necesita un diseño unidimensional se una flexbox, si se necesita un diseño bidimensional se usa css grid

## TERMINOS IMPORTANTES

- `display: grid;` GRID CONTAINER -> contenedor cuadrícula
- GRID ITEMS -> los elementos secundarios del grid container
- ROW AXIS
- COLUMN AXIS
  **NO SE PUEDE CAMBIAR LA DIRECCION DE LOS EJES COMO EN FLEXBOX**
- GRID LINES -> líneas de cuadrícula, son las líneas que dividen la cuadrícula. Se numeran del 1 hasta n+1 (n = número de columnas/filas)
  La intersección de las líneas de las filas y las líneas de columnas crean las áreas donde colocar los grid items.
- GRID CELL -> las areas que se forman de la interseccion de las grid lines columns y grid lines rows
- GUTTERS (GAPS) -> los espacios que se forman entre las GRID CELL
- GRID TRACK/ROW -> es una fila de la grilla ejemplo 2 row tracks
- GRID TRACK/COLUMN -> es una columna de la grilla ejemplo 3 column tracks
  Se llaman tracks porque estos conceptos son mas sobre el espacio en sí y no sobre los grid items

## GRID CONTAINER

- `grid-template-rows: <track size>`
- `grid-template-columns: <track size>`
  Para establecer las track rows y track columns de la cuadrícula. Una unidad de longitud para cada track. Se puede usar cualquier unidad, fr llenan el espacio no utilizado

  - AUTO para el valor de alguna fila o columna, el tamaño es el del contenido
  - `<track size> = repeat(cantidad, tamaño)` -> establecer cuantas columnas y de que tamaño dibujar
  - Las filas que se especifica el tamaño se llaman EXPLICITAS. las que se forman automaticamente por falta de espacio se llaman IMPLICITAS
  - Las filas que se especifica el tamaño en FR hace que los grid items crezcan al valor del item de mayor valor llenando el espacio disponible de la fila. En caso que no se especifique tamaño, éste será el del contenido del item

- `row-gap: 0 | <lenght>`
- `column-gap: 0 | <lenght>`
  Juntos forman
- `gap: 0 | <lenght>`
  Para crear espacios vacíos entre tracks

- `justify-items: stretch (valor por defecto) | start | center | end`
- `align-items: stretch (valor por defecto) | start | end | center | end`
  Para alinear elementos dentro de las filas o columnas (horizontalmente / verticalmente)
  Stretch -> estira los elementos al tamaño del elemento de mayor tamaño
  start - center - end -> el tamaño es el del contenido

- `justify-content: start | center | end`
- `align-content: start | center | end`
  Para alinear la cuadrícula completa dentro del contenedor de la cuadrícula. Solo aplica si el contenedor es más grande que la rejilla

## GRID ITEMS

- `grid-column: <start line> / <end line> | span <number>`
- `grid-row: <start line> / <end line> | span <number>`
  Para colocar un elemento de la cuadrícula en una celda específica, según los números de línea.
  La palabra clave SPAN se puede utilizar para distribuir un elemento en más celdas.
  Para llevar un item hasta el final usar -1, que es el valor mas a la derecha.
  Para las filas es de derecha a izquierda (-n, ..., -3, -2, -1)
  Para las columnas es de abajo hacia arriba
  -n,
  ...,
  -3,
  -2,
  -1

- `justify-self: stretch | start | center | end`
- `align-self: stretch | start | center | end`
  Para sobrescribir justify-items / align-items para elementos individuales

## [CHALLENGE #4 CSS GRID](https://codepen.io/PatriciaVendrame/pen/eYEzbQy)
