## ¿Qué es un service worker?

Un service worker es una secuencia de comandos ejecutados por el navegador en segundo plano. Se trata de un fichero JavaScript que continúa ejecutándose aunque el sitio web esté cerrado.

Estas son las características más destacadas de un service worker:
* No puede acceder directamente al DOM, sino que se comunica con las páginas que controla mediante la interfaz PostMessage.
* Al ser un proxy de red programable, permite controlar el modo en que se manejan las solicitudes de red de la página.
* Son capaces de mantener información mediante la API de IndexedDB.
* Pueden implementar diferentes sistemas de cacheo.
