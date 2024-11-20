El ciclo de vida de una página HTML tiene tres eventos importantes:

* DOMContentLoaded – el navegador HTML está completamente cargado y el árbol DOM está construido, pero es posible que los recursos externos como <img> y hojas de estilo aún no se hayan cargado.
* load – no solo se cargó el HTML, sino también todos los recursos externos: imágenes, estilos, etc.
* beforeunload/unload – el usuario sale de la pagina.
  document.readyState es el estado actual del documento, los cambios se pueden rastrear con el evento readystatechange:
  
      loading – el documento esta cargando.
      interactive – el documento se analiza, ocurre aproximadamente casi al mismo tiempo que DOMContentLoaded, pero antes.
      complete – el documento y los recursos se cargan, ocurre aproximadamente casi al mismo tiempo que window.onload, pero antes.


Cada evento puede ser útil:

* Evento DOMContentLoaded – DOM está listo, por lo que el controlador puede buscar nodos DOM, inicializar la interfaz.
* Evento load – se cargan recursos externos, por lo que se aplican estilos, se conocen tamaños de imagen, etc.
* Evento beforeunload – el usuario se va: podemos comprobar si el usuario guardó los cambios y preguntarle si realmente quiere irse.
* Evento unload – el usuario casi se fue, pero aún podemos iniciar algunas operaciones, como enviar estadísticas.
