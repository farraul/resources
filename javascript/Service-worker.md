## ¿Qué es un service worker?

Un service worker es una secuencia de comandos ejecutados por el navegador en segundo plano. Se trata de un fichero JavaScript que continúa ejecutándose aunque el sitio web esté cerrado.

Estas son las características más destacadas de un service worker:
* No puede acceder directamente al DOM, sino que se comunica con las páginas que controla mediante la interfaz PostMessage.
* Al ser un proxy de red programable, permite controlar el modo en que se manejan las solicitudes de red de la página.
* Son capaces de mantener información mediante la API de IndexedDB.
* Pueden implementar diferentes sistemas de cacheo.


## ¿Cómo agregar un service worker?
Podemos agregar un service worker de manera sencilla: bastará con crear el archivo que contiene el código de script y posteriormente registrarlo mediante el register() del API del navegador.  Lo vemos paso a paso:

* 1. Crear el archivo JavaScript de tu service worker. Lo primero que haremos es crear el archivo JavaScript sw.js y lo emplazaremos en el raíz del sitio web. Suele estar ubicado en el mismo nivel del index.html. Para comenzar podemos colocar el archivo sw.js en blanco, aunque es interesante saber que existen diferentes librerías y servicios para generar código de service worker y facilitarnos la tarea, como por ejemplo el Workbox creado por Google.
* 2. Registrar el service worker. Una vez creado el archivo sw.js, registraremos el service worker con ayuda de más código JavaScript. Este proceso puede tramitarse a través de una sola llamada a un método del API de los service worker del navegador. Para ello deberemos cerciorarnos de que el cliente  soporta dicha tecnología. Este es un ejemplo del código para registrar el Service Worker:
   
![image](https://github.com/user-attachments/assets/48201f77-7bb4-4a66-b77c-ff404facfcfb)

* 3. Ver el service worker registrado. Para verificar si hemos registrado correctamente el service worker, podremos comprobarlo a través de las herramientas de desarrollador, como por ejemplo Chrome Developer Tools.
