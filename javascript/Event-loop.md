
## Que es Event Loop
También conocido como bucle de eventos en programación, es un mecanismo fundamental que existe en algunos lenguajes de programación, como JavaScript, para gestionar la ejecución de tareas de forma eficiente y no bloqueante.

En términos sencillos, el event loop es como un vigilante que está continuamente atento a la aparición de nuevos eventos o tareas para ser procesadas

## Task Queue (prioridad)
1. Tareas de Javascript
2. MicroTareas de la WebAPI
3. Tareas de la WebAPI


#### WebAPI
Acciones que puede ejecutar un navegador y añadirlas a la CallStack ayudando a optimizar el rendimiento de una web.
No es parte del lenguaje de Javascript sino de las APIs que usamos:
* setTimeout
* fetch
* Promesas
* Intersection Observer

## Task Javascript (tarea)
Son acciones de Javascript.

 ![image](https://github.com/user-attachments/assets/f2d4cbd1-ea1c-4eaf-94ae-708494423fdc)

## Microtask (micro tarea)
Microtareas son acciones de las Web WebAPIs que se ordenan en la cola de tareas.
* Son tareas más sencillas
* Tienen mayor prioridad
* Se ejecutan entre tareas
* Promesas: Promise.then, Promise.catch, Promise.finally.
* Mutations: MutationObserver.
  
    ![image](https://github.com/user-attachments/assets/a40572e3-9371-4278-8946-097784890fd5)


## Task WebAPI (tarea)
Tarea o MacroTarea. Son acciones de Javascript y WebAPI.

Son acciones pesadas para el navegador.

* Eventos del DOM: Clicks, teclas presionadas, etc.
* Timers: setTimeout, setInterval.
* Operaciones asíncronas: Como las solicitudes AJAX.

![image](https://github.com/user-attachments/assets/7f1eba3d-a42d-435a-8fda-fc7ce6365790)


### Ejemplo
![image](https://github.com/user-attachments/assets/f5d8d5f0-2b4f-4ec0-b411-b7ebfd124f79)



## Call stack
Mecanismo de como, cuando, y el orden de ejecutar las funciones de javascript.  

setTimeout (WebApis)

Promise (WebApis)

## Ejemplo

    console.log('Inicio');
    
    setTimeout(() => {
      console.log('Tarea: setTimeout');
    }, 0);
    
    Promise.resolve().then(() => {
      console.log('Microtarea: Promise');
    });
    
    console.log('Fin');

 Consola:

    Inicio
    Fin
    Microtarea: Promise
    Tarea: setTimeout

   ## Ejemplo 2
   
    console.log('Inicio');
    
    setTimeout(() => {
     console.log('Tarea: setTimeout');
    }, 0);
    
    Promise.resolve().then(() => {
     console.log('Microtarea: Promise 1');
    }).then(() => {
     console.log('Microtarea: Promise 2');
    });
    
    const observer = new MutationObserver(() => {
     console.log('Microtarea: MutationObserver');
    });
    
    const targetNode = document.createElement('div');
    observer.observe(targetNode, { attributes: true });
    
    targetNode.setAttribute('id', 'nuevo-id');
    
    console.log('Fin');

   Consola:

    Inicio
    Fin
    Microtarea: Promise 1
    Microtarea: Promise 2
    Microtarea: MutationObserver
    Tarea: setTimeout


   

## Referencia
https://www.youtube.com/watch?v=rvzItyLuh28


