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
