# **FUNDAMENTOS DE CSS**

## QUE ES CSS?

- CSS es Cascading Style Sheets - Hojas de Estilos en Cascada

- CSS describe el estilo visual y la presentación del contenido que se escribe previamente con HTML

- Css consta de innumerables propiedades que los desarrolladores usan para formatear al contenido: propiedades de fuentes, textos, espacios, diseños de pagina, etc

- Elementos que componen un estilo de css

```css
h1 {
  color: blue;
  text-align: center;
  font-size: 20px;
}

/*
selector {
  propiedad: valor; 
  ....
  mas declaraciones o estilos
}
*/
```

- Todas las declaraciones o estilos juntos componen el bloque de declaración (bloque entre llaves)

- REGLA CSS es el selector mas el bloque de declaración

- ESCRIBIR REGLAS CSS: tres formas
  - CSS en linea: escribir css dentro del elemento `<h1 style="color: blue">`
  - CSS interno: dentro del head se escriben las etiquetas `<style></style>` dentro de las cuales se escriben las reglas css
  - CSS externo: un archivo especial donde estan todas las reglas css, el mismo se vincula con el html en el head mediante la etiqueta `<link href="style.css" rel="stylesheet">`, href es la ruta del archivo a vincular y rel es el tipo de archivo que se vincula.

## PROPIEDADES DE CSS

- color -> color al texto

- font-size -> tamaño del texto

- font-family -> tipo de fuente del texto

- text-transfrom -> cambia el texto a todo mayúsculas, todo minúsculas o capitaliza la primera letra de cada palabra (uppercase, lowercase, capitalize)

- font-style -> estilos como itálica, oblicua, heredada, etc

- line-height -> especifica la altura de la línea en relación al tamaño de la fuente

- text-align -> alinea el texto en el documento

- background-color -> darle color al fondo del elemento

- border: aplicar border al elemento

- Combinar Selectores -> separar los selectores con comas (ejemplo h1, h2, h3 {estilos})

- Selector Descendiente -> separar los selectores por un espacio, se aplica de padres a hijos segun se escriban en el html

- Selector de Clase y Selector de ID -> aplicar estilos mediante el nombre del id y clases, para id es #selector, en las clases .selector

- Atributos de id y clases -> se agregan a los elementos en el html. Los atributos de ID no se pueden repetir a lo largo del documento, los atributos de clases se pueden repetir

## COLORES EN CSS

- RGB -> colores representados por combinación de ROJO, VERDE Y AZUL (RED, GREEN, BLUE), los valores van de 0 a 255

  - ROJO -> `rgb(255, 0, 0)`
  - VERDE -> `rgb(0, 255, 0)`
  - AZUL -> `rgb(0, 0, 255)`
  - BLANCO -> `rgb(255, 255, 255)`
  - NEGRO -> `rgb(0, 0, 0)`

- RGBA -> canal alpha que es transparencia, valor de 0 a 1

- HEXADECIMAL -> los colores van de 00 a FF
  - ROJO -> `#FF0000 o #f00`
  - VERDE -> `#00FF00 o #0f0`
  - AZUL -> `#0000FF o #00f`
  - BLANCO -> `#FFFFFF o #fff`
  - NEGRO -> `#000000 0 #000`

## PSEUDOCLASES EN CSS

Se escribe selector:pseudoclase

- :first-child -> selecciona el primer hijo del contenedor al que se le aplica
- :last-child -> selecciona el ultimo hijo del contenedor al que se le aplica
- :nth-child(numero) -> selecciona un hijo específico del contenedor al que se aplica. Se pueden usar palabras como parámetro, ODD para los impares y EVEN para los pares

Las pseudoclases funcionan perfecto cuando los elementos hijos son todos iguales, de esa manera se puede seleccionar le primer hijo por ejemplo.
Cuando se mezclan selectores padres con selectores hijos no funciona bien ya que siempre se aplica al elemento hijo directo del contenedor
Ejemplo article p:first-child va a seleccionar el primer hijo del contenedor que si no es un parrafo no va a aplicar ningun estilo.

- a:link -> aplica estilos a todas las anclas que tienen un link en su href
- a:visited -> aplica estilos cuando un enlace ya ha sido visitado
- a:hover -> aplica estilos cuando el puntero esta sobre el elemento
- a:active -> luego de hacer click en el elemento se edita mientras se sostiene el click

## CONFLICTO ENTRE SELECTORES

Segun su importancia, se aplican segun el siguiente orden:

- (0) -> DECLARACION !IMPORTANT
- (0.1) -> ESTILO EN LINEA
- (1) -> ID selector, si hay múltiples ID se aplica el último declarado
- (2) -> CLASS selector o PSEUDOCLASE selector, se aplica el último que se declaro
- (3) -> SELECTOR DE ELEMENTO -> se aplica el último declarado
- (4) -> SELECTOR UNIVERSAL -> tiene la prioridad mas baja, especificidad 0

## HERENCIA

Mecanismo por el cual algunas propiedades obtienen sus valores heredados de elementos principales a elementos secundarios, los hijos heredan de los padres.
El elemento principal es BODY, es el padre de todos los demas elementos del documento HTML.
No todas las propiedades se heredan, sobre todo las que se relacionan con los textos. Los estilos heredados se sobreescriben facilemente con alguna regla que anule el estilo heredado para la misma propiedad

- `*` -> es el selector universal, selecciona todos los elementos del documento, es útil cuando queremos aplicar una cierta propiedad a todos los elementos (propiedad que se aplica a cada una de las etiquetas del html) pero si es una propiedad que no se hereda, en caso que sea necesario que sea heredada debe ir en el body

## MODELO DE CAJA - BOX MODEL

- Define como se muestran los elementos en una pagina web y su tamaño
- Componentes del box-model
  - CONTENT -> el contenido real del elemento, se puede establecer el alto y el ancho usando una propiedad CSS
  - BORDER -> el borde del elemento
  - PADDING -> espacio entre el contenido y el borde
  - MARGIN -> espacion entre el borde y el entorno, no pertenece al calculo del interior de la caja (borde, contenido y padding)
  - Cuando no se especifican alto y ancho, el tamaño del contenido es el que tiene el texto
- Para resetear los estilos que los elementos traen por defecto se agrega en el html las propiedades padding=0 y margin=0, como en el body se colocan las propiedades relacionadas con los textos y son heredables, estas propiedades deben aplicarse a cada uno de los elementos del documento por lo que se agregan en el html
- Colapso de margenes, cuando dos margenes se superponen, css opta por colapsar los margenes y dejar el que tiene el valor mas grande

## DIMENSIONES

- HEIGHT -> establece el alto del elemento
- WIDTH -> establece el ancho del elemento
- Modificar el alto y el ancho en css de un elemento cuando estas propiedades también están el el html, al sobreescribir una de ellas la otra debe tener el valor "auto"
- Establecer el alto y el ancho en el css, al establecer una sola por defecto la otra se ajusta a la imagen para que quede proporcionada.
- WIDTH: 100% -> hace que el elemento se adapte al ancho de la pantalla y ocupe siempre el 100% de la misma

## CENTRAR UNA PAGINA

- Crear un contenedor que contenga todo el documento html
- Dar un ancho al elemento mayor al de sus elementos hijos
- Establecer los márgenes izquierdo y derecho en auto, esto hace que ambos midan lo mismo pero que se calculen automáticamente. Al agrandar o achicar el tamaño de la pantalla a una resolución mayor a la establecida en el width, el contenido se adapta y los márgenes se calculan para que sigan siendo del mismo tamaño

## TIPOS DE CAJAS

- INLINE ->

  - cajas que ocupan el espacio que necesitan para su contenido
  - No generan saltos de línea antes o después del elemento
  - No se puede aplicar HEIGHTS y WIDTHS
  - PADDING y MARGIN se aplican solamente de manera horizontal, es decir a la izquierda y derecha del elemento. Aplicar padding a un elemento en linea expande el tamaño del elemento pero no crea un espacio que desplace el elemento como si ocurre con los elementos en bloque. El elemento sigue estando en el mismo lugar aunque las dimensiones de la caja se modifiquen sobreponiendose a los elementos colindantes

- BLOCK ->

  - cajas a nivel bloque o elementos a nivel bloque
  - ocupan todo el espacio que pueden y crean saltos de linea despues de ellos, es decir, no pueden estar uno al lado del otro - ocupan el 100% del ancho del elemento padre no importa el contenido

- INLINE-BLOCK ->

  - Solo ocupan el espacio que necesitan para el contenido y no provocan saltos de linea
  - Se puede aplicar height, width, padding y margin

## POSICION ABSOLUTA - ABSOLUTE POSITION

- POSITION RELATIVE -> es la posición por default, los elementos siguen el flujo del documento, en el orden del HTML

- POSIITION ABSOLUTE ->
  - Permite posicionar los elementos en cualquier lado de la página. El elemento sale del flujo normal de la página y se dice que esta fuera de flujo.
  - Este elemento pierde completamente cualquier impacto en los elementos circundantes, incluso puede superponerse a estos.
  - Se puede usar las propiedades top, right, bottom y left para posicionar el elemento y este posicionamiento va a suceder en relación a un contenedor relativamente posicionado
  - Si la posicion absoluta es fuera del contenedor, se ubica en la posicion que indiquemos pero del viewport, la parte visible del documento
- Donde declaremos position: relative se colocara de manera absoluta el elemento

## PSEUDOSLASES - PSEUDOELEMENTOS

Gracias a las pseudoclases y los pseudoelementos de CSS podemos realizar una selección mas específica de los elementos a los que queremos aplicar un cierto estilo sin necesidad de crear una clase concreta

Las pseudoclases describen un estado

### PSEUDOCLASES para la selección de hijos o hermanos

- :first-child -> primer hijo
- :last-chiild -> último hijo
- :first-of-type -> primer hermano en su tipo
- :last-of-type -> último hermano en su tipo
- :only-child -> hijos únicos
- :only-of-type -> únicos hermanos de su tipo
- :empty -> elementos que no tienen hijos
- :nth-child(n) -> enésimo elemento hijo
- :nth-last-child(n) -> enésimo elemento hiijo contando desde el último
- :nth-of-type(n) -> enésimo hermano de su tipo
- :nth-last-of-type(n) -> enésimo hermano de su tipo comenzando desde el último

### PSEUDOCALSES para los estados de un elemento

- :link -> no visitado por el usuario, todos los elementos que tienen un link en su href
- :visited -> visitado por el usuario
- :hover -> modifica el estilo cuando un elemento apuntador pasa por encima
- :active -> se activa cuando el usuario pulsa el elemento
- :focus -> se activa cuando tiene el foco sobre el elemento

### PSEUDOELEMENTOS

Permiten añadir estilos a una parte específica del documento.

- ::first-line -> primera línea de texto de un elemento|
- ::first-letter -> primera letra de la primera línea de texto de un elemento
- ::before -> añade el contenido al principio del documento
- ::after -> añade el contenido al final del documento
- ::selection -> toma la porción del texto que se está seleccionando por el usuario

- ::before y ::after -> en necesario establecer la propiedad CONENT, que puede tener un string vacio o un texto pero siempre debe estar

  - el elemento agregado es un elemento inline
  -

- `(selector + selector {propiedades})` -> donde "+" es el HERMANO ADYACENTE de un elemento es el hermano que viene inmediatamente despues
  Ejemplo: h3 + p selecciona todos los parrafos que aparecen inmediatamente despues de todos los h3
