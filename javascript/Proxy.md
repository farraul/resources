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

  ![image](https://github.com/user-attachments/assets/ec602d82-1892-4ee0-ac90-db7ef2898726)

