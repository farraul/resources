### Resumen

window: Objeto global que contiene tanto el DOM como el BOM.

DOM: Representa el contenido del documento HTML y permite su manipulación.

BOM: Permite la interacción con el navegador y su entorno.



## DOM (Document Object Model)
El DOM es una representación estructurada del documento HTML. Permite a JavaScript acceder y manipular el contenido, estructura y estilo de los documentos.

### Propiedades:

* document: Es la raíz del DOM y representa el documento HTML.
* document.title: Obtiene o establece el título del documento.
* document.body: Representa el elemento <body> del documento.

### Métodos:

* document.getElementById(id): Devuelve el elemento con el ID especificado.
* document.querySelector(selector): Devuelve el primer elemento que coincide con el selector CSS especificado.
* document.createElement(tagName): Crea un nuevo elemento HTML.
* document.appendChild(node): Añade un nodo como último hijo de un nodo padre.

## BOM

### Propiedades:
* window.innerHeight: Devuelve la altura interna de la ventana del navegador en píxeles.
* window.innerWidth: Devuelve la anchura interna de la ventana del navegador en píxeles.
* window.outerHeight: Devuelve la altura externa de la ventana del navegador en píxeles.
* window.outerWidth: Devuelve la anchura externa de la ventana del navegador en píxeles.
* window.screen: Proporciona información sobre la pantalla del usuario.
* window.location: Proporciona la URL de la ventana actual y permite redirigir a nuevas URLs.
* window.history: Permite interactuar con el historial de navegación del navegador.
* window.navigator: Proporciona información sobre el navegador del usuario.
* window.screenX: Devuelve la coordenada X de la ventana del navegador relativa a la pantalla.
* window.screenY: Devuelve la coordenada Y de la ventana del navegador relativa a la pantalla.

### Métodos
* window.alert(message): Muestra un cuadro de alerta con un mensaje.
* window.confirm(message): Muestra un cuadro de diálogo con opciones de "Aceptar" y "Cancelar".
* window.prompt(message, default): Muestra un cuadro de diálogo que solicita al usuario que ingrese un valor.
* window.open(url, name, specs): Abre una nueva ventana o pestaña del navegador con las especificaciones dadas.
* window.close(): Cierra la ventana actual.
* window.scrollTo(x, y): Desplaza la ventana a una posición específica.
* window.scrollBy(x, y): Desplaza la ventana por una cantidad específica.
* window.setTimeout(function, milliseconds): Ejecuta una función después de un retraso especificado.
* window.setInterval(function, milliseconds): Ejecuta una función repetidamente a intervalos especificados.
* window.clearTimeout(timeoutID): Cancela una acción programada con setTimeout.
* window.clearInterval(intervalID): Cancela una acción programada con setInterval.
