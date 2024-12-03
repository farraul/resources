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
