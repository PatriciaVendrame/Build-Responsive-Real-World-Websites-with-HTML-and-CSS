# **FUNDAMENTOS DE HTML**

### **HTML**

- HTML -> HyperText Markup Language (lenguaje de marcado de hipertexto)

- No es un lenguaje de programacion

- Usado por los desarrolladores web para ESTRUCTURAR Y DESCRIBIR CONTENIDO en la página web

- Consiste en elementos que describen diferentes tipos de contenido: parrafos, enlaces, headings, imagenes, videos, etc

- Los navegadores entienden HTML y lo representtan como sitio web

- Un elemento en HTML consta de tres partes:

  - ETIQUETA DE APERTURA que es el nombre del elemento entre <>
  - EL CONTENIDO del elemento que puede ser texto u otro contenido como un elemento hijo
  - ETIQUETA DE CIERRE </>. Hay elementos como las imagenes que no tienen contenido ni etiqueta de cierre, los elementos sin contenido de texto no llevan etiqueta de cierre.

- `<!DOCTYPE html>` -> indica que se va a escribir codigo html. Le permite saber al navegador que debe usar la especificacion HTML 5 para renderizar el archivo

- Estructura de un documento HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <!--elementos no visibles en el documento -->
  </head>

  <body>
      <!--elementos visibles en el documento -->
</html>
  </body>
```

---

_**HEADINGS:**_ El objetivo de los headings o encabezados es dividir grandes bloques de texto en secciones mas logicas agregando un titulo a cada una de las secciones.

**_TAGS:_**

- `<!-- -->` comentarios y para ocultar codigo en html
- `<h1>` a `<h6>` es una jerarquia de encabezados, es una buena práctica tener un h1 por página web
- `<p></p>` para marcar bloques de texto mas grandes
- `<b></b>` -> bold o negrita sin sentido semántico
- `<bold></bold>` -> bold o negrita su sentido semántico es contenido que se pretende destacar, en uso a partir de HTML 5,
- `<i></i>` -> cursiva o itálica sin sentido semantico
- `<em></em>` ->(emphasis) cursiva o itálica su sentido semantico es dar énfasis al texto
- `<ol></ol>` -> order list (lista orenada), enumera los elementos que contiene
- `<ul></ul>` -> unorder list (lista desordenada), los elementos no tienen un orden establecido
- `<li></li>` -> list item (item de lista) para crear elementos en las listas
- `<img/>` -> para insertar imagenes, como no tiene contenido no tiene etiqueta de cierre. Contiene atributos que son datos que se usan para describir elementos
- `<meta >` -> metadatos que significa datos sobre los datos
- `< a >` -> ancla, hipervínculos, link o enlaces que apuntan a otras paginas de nuestro propio sitio web y los que apuntan a enlaces fuera de nuestro sitio web
- `<nav>` -> navegacion, agrupa los elementos el menu de navegacion
- `<header>` -> encabezado, significa la parte superior de un documento web o tambien la parte superior de alguna unidad mas pequeña.
- `<article>` -> es un contenedor de bloques de contenido que se consideran independientes del sitio web y pueden, por lo tanto, ser vistos, reutilizados y distribuidos por separado
- `<div>` -> cuando se define una caja que no necesita sentido semántico
- `<aside>` -> para información secundaria que complementa la información en la parte principal de la página, están relacionada con la parte principal.

**_ATRIBUTOS EN HTML_**

- `< src = "ruta" >` = (source) -> describe la fuente desde la cual el navegador deberia leer el archivo por ejemplo, una imagen
- `< alt="descripción" >` = texto alternativo -> describe la imagen y nunca debe faltar ya que es importante para los motores de busquedas y los lectores que usan las personas ciegas. Cuando la carga de la imagen falla, se muestra el texto alternativo
- `<html lang="es">` -> atributo para especificar el idioma que se usa en la web.
- `< meta charset="UTF-8">` Especificar el juego de caracteres que se usaran en el documento. UTF-8 son todos los caracteres simples que se usan en el idioma de escritura del documento
- `<a href="url>"` -> href es la abreviatura de Hipertext Reference, o lo que es lo mismo Referencia de Hipertexto. En este atributo es donde indicamos el URL a la que apuntaremos con el enlace. Pueden ser enlaces a paginas externas (href="https://google.com.ar"), enlaces a paginas dentro del mismo sitio (href="blog.html") o enlaces que no van a ninguna parte (href="#")
- `<a href="url" target ="_blank"` ->El atributo target indica al navegador dónde abrir la página o documento enlazado. "\_blank", coloquialmente llamado target_blank, es un atributo HTML que se puede colocar en un enlace para indicar que la página de destino hacia la que apunta se abra en otra ventana del navegador
- `&copy;` -> entidades en HTML. Las entidades son unas estructuras que, mediante el uso de una codificación, nos permiten representar un símbolo. La estructura de la entidad HTML es un ampersand(&) seguido del código o nombre de la entidad y terminado en un punto y coma.

## **HTML SEMANTICO**

Ciertos elementos se les atribuye un significado o propósito, ver cada elemento como lo que significa y lo que representa. No todos los elementos son semánticos
Se utiliza para la optimizacion de los motores de busqueda como los de Google, esto significa que puede comprender la estructura del contenido y de que se trata el sitio web. También es muy importante en términos de accesibilidad y especialmente para las personas que dependen de los lectores de pantallas para consumir contenido web

---

## **CHALLENGE #1**

[CHALLENGE #1 ENLACE CODEPEN](https://codepen.io/PatriciaVendrame/full/QWgzgLG)
