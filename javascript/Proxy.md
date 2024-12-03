Tenemos get y set

 get: function(target, property) {}
 set: (target, property, value) => {
 
 * Target es el names cuando se crea el proxy:
    let proxy = new Proxy(names, {...}
* Property es "value":
   proxyT.value = "pepito";
  * Value es "pepito"
     proxyT.value = "pepito";

   
## Ejemplo 1    
    (function() {
      let names = ["Juan", "Pedro", "Héctor"];
    
      let proxy = new Proxy(names, {
        get: function(target, property) {
          console.log(property);
          console.log(target)
        }
      });
    
      console.log(proxy['nuevo-property']);
      })();

![image](https://github.com/user-attachments/assets/aecd8353-2ecf-4f0a-b66f-6ff881873fb9)

## Ejemplo 2

        (function() {
          let names = ["Juan", "Pedro", "Héctor"];
        
          let proxy = new Proxy(names, {
            get: function(target, property) {
              return target[property];
            }
          });
        
          console.log(proxy[0]);
        })();

        // Juann

## Ejemplo 3

        (function() {
          let names = ["Juan", "Pedro", "Héctor"];
        
          let proxy = new Proxy(names, {
            get: function(target, property) {
              return property === 'length' ?
                target.length :
                target[property]?.toUpperCase();
            },
            set: (target, property, value) => {
              if (typeof(value) === 'string') {
                target[property]   = value;   
                //target.push(value)   en este caso no usará el property "5"
              }
            }
          });
          
          proxy[5] = "Camila";
          for (let i = 0; i < proxy.length; i++) {
            console.log(proxy[i]);
          }
        })();

![image](https://github.com/user-attachments/assets/f0d5401b-cc1e-4103-bb0c-65b64a7ca3ec)

## Ejemplo 4 (proxy para el DOM)

        // Se crea un nuevo proxy para el elemento con id "txt"
        let proxyT = new Proxy(document.getElementById("txt"), {
          // Trampa para obtener el valor de una propiedad
          get: (target, property) => {
            // Si la propiedad es "content", devuelve el valor del elemento
            if (property === "content") {
              return target.value;
            }
            // Si no es "content", devuelve el valor de la propiedad del target
            return target[property];
          },
          // Trampa para establecer el valor de una propiedad
          set: (target, property, value) => {
            // Si la propiedad es "value", convierte el valor a mayúsculas antes de asignarlo
            if (property === "value") {
              target[property] = value.toUpperCase();
            }
          }
        });
        
        // Se imprime en la consola el valor de la propiedad "content" del proxy
        console.log(proxyT.content);
        
        // Se asigna el valor "pepito" a la propiedad "value" del proxy,
        // lo cual se convertirá a mayúsculas debido a la trampa "set"
        proxyT.value = "pepito";
