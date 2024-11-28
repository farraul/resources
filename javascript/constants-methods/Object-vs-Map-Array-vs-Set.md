https://es.javascript.info/map-set

##  Map (similar to objects)
* Cuando el orden es importante: Si necesitas mantener el orden de inserción de los elementos. En los objetos no te puedes fiar.
* La principal diferencia es que Map permite claves de cualquier tipo (incluyendo funciones, objectos...). En objetos solo pueden ser String o Symbol.
* Si se va aplicar un delete de una key fastidia el rendimiento con el map se soluciona.
* El map va muy bien se si va a hacer añadir y borrar.

#### Ejemplo llamada API
    async function almacenarDatosEnMap(map, datos) {
      // Iteramos sobre los datos
      for (const dato of datos) {
        // Suponemos que cada dato tiene un ID único
        const id = dato.id;
        map.set(id, dato);
      }
    }
    
    // Datos de ejemplo (simulando una respuesta de la API)
    const datosUsuarios = [
      { id: 1, nombre: 'Ana', edad: 25 },
      { id: 2, nombre: 'Carlos', edad: 30 },
      { id: 3, nombre: 'Sofía', edad: 28 }
    ];
    
    // Crear un Map para almacenar los datos
    const cacheUsuarios = new Map();
    
    // Llamar a la función para almacenar los datos
    await almacenarDatosEnMap(cacheUsuarios, datosUsuarios);

## Set (similar to arrays)
* Cada valor puede aparecer solo una vez.

### Tabla
![image](https://github.com/user-attachments/assets/6c9da313-664e-404e-aab8-36a3e3adcaa8)





## WeakSet (similar to set)


#### WeakSet 
    Ejemplo con WeakSet:
    
    JavaScript
    // Creamos un WeakSet para almacenar referencias a elementos DOM
    const elementosProcesados = new WeakSet();
    
    // Creamos algunos elementos DOM
    const div1 = document.createElement('div');
    const div2 = document.createElement('div');
    
    // Agregamos los elementos al WeakSet
    elementosProcesados.add(div1);
    elementosProcesados.add(div2);
    
    // Simulamos el procesamiento de un elemento
    function procesarElemento(elemento) {
      console.log('Procesando elemento:', elemento);
      // Aquí iría la lógica para procesar el elemento
    }
    
    // Procesamos el primer elemento
    procesarElemento(div1);
    
    // Eliminamos todas las referencias al primer elemento
    div1 = null;
    
    // El garbage collector puede eliminar div1, y automáticamente se eliminará del WeakSet
    console.log(elementosProcesados.has(div1)); // Esto dará false



#### Set

    const elementosProcesados = new Set();
    
    // Creamos algunos elementos DOM
    const div1 = document.createElement('div');
    const div2 = document.createElement('div');
    
    // Agregamos los elementos al Set
    elementosProcesados.add(div1);
    elementosProcesados.add(div2);
    
    // Simulamos el procesamiento de un elemento
    function procesarElemento(elemento) {
      console.log('Procesando elemento:', elemento);
      // Aquí iría la lógica para procesar el elemento
    }
    
    // Procesamos el primer elemento
    procesarElemento(div1);
    
    // Eliminamos todas las referencias al primer elemento
    div1 = null;
    
    // El garbage collector puede eliminar div1, pero div1 seguirá estando en el Set
    console.log(elementosProcesados.has(div1)); // Esto dará false, pero div1 aún ocupa memoria
