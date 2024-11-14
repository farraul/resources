
### PWA (Progressive web apps)
Queremos pasar nuestra aplicación de React a una PWA.
Ayuda a que los clientes tengan una mejor experiencia en nuestra aplicación de React.
Ayuda a realizar menos peticiones hacia nuestro  backend.


### Service Worker
El service worker es como un proxy. 

React <-> Service worker <-> Backend.

Los trabajadores del servicio son **scripts** que controlan la forma en que un navegador web maneja las solicitudes de red y el almacenamiento en caché de activos. Con la ayuda de los service workers, los desarrolladores web crean páginas web confiables y rápidas que también pueden funcionar sin conexión.

El Service Workers es realmente importante ya que nos permite optimizar la retención de los usuarios. Hasta la fecha, esta funcionalidad solo la tenían las aplicaciones nativas, pero se ha convertido en una de las funcionalidades más importantes para poder mejorar el retorno del usuario a nuestra app. No obstante, con el aumento de notificaciones en todas las app, esta funcionalidad o característica cada vez queda más oculta.

### Archivo de manifiesto

El archivo de manifiesto es un archivo JSON.

Su función principal es controlar la forma en que una aplicación aparece para los usuarios finales. Además, garantiza la visibilidad de las PWA al describir el nombre de la aplicación, la URL de inicio, los íconos y cualquier información adicional para cambiar del formato del sitio web a uno de la aplicación.

Esto es lo que suele incluir el archivo JSON:

Name: Nombre de la aplicación que aparecerá en el menú mobile del usuario.
Description: Indicar la descripción de nuestra aplicación móvil
Icons: Crear distintos iconos, con resoluciones distintas, para que de esta manera, se vea bien en todos los dispositivos.
Start url: URL de inicio cuando abrimos la aplicación
Display: En este caso, podemos elegir varias configuraciones (standalone, fullscreen, minimal-ui, entre otros)
Orientation: Cuando hablamos de orientación nos referimos a si queremos que la aplicación web se deba usar en modo retrato o en modo paisaje.
Theme_color: el color que se usará para la barra superior de la aplicación.
Background_color: color para la pantalla antes de la carga completa de la aplicación.

## info

El service worker está más abajo de mi  index.js
