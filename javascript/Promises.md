
## Sin catch

        let promise = new Promise(function(resolve, reject) {
          setTimeout(() => reject(new Error("Whoops!")), 1000);
        });
        
        // reject runs the second function in .then
        promise.then(
          result => alert(result), // doesn't run
          error => alert(error) // shows "Error: Whoops!" after 1 second
        );

### Con catch
Los errores también pueden ser manejados usando .catch. La diferencia es que .catch se usa específicamente para manejar errores, mientras que .then puede manejar tanto el éxito como el error. Aquí tienes cómo podrías reescribir tu código usando .catch:


        let promise = new Promise(function(resolve, reject) {
          setTimeout(() => reject(new Error("Whoops!")), 1000);
        });
        
        // reject runs the .catch function
        promise.then(
          result => alert(result) // doesn't run
        ).catch(
          error => alert(error) // shows "Error: Whoops!" after 1 second
        );




### Ignorado

        let promise = new Promise(function(resolve, reject) {
          resolve("done");
        
          reject(new Error("…")); // ignored
          setTimeout(() => resolve("…")); // ignored
        });


  ### Then      
        let promise = new Promise(function(resolve, reject) {
          setTimeout(() => resolve("done!"), 1000);
        });
        
        // resolve runs the first function in .then
        promise.then(
          result => alert(result), // shows "done!" after 1 second
          error => alert(error) // doesn't run
        );
        

## Promesas
### Promise.all

Si necesitas realizar múltiples solicitudes en paralelo y esperar a que todas se completen, puedes usar Promise.all:


        async function fetchMultipleData() {
          try {
            const [data1, data2] = await Promise.all([
              fetch('/api/data1').then(response => response.json()),
              fetch('/api/data2').then(response => response.json())
            ]);
            console.log('Datos recibidos:', data1, data2);
          } catch (error) {
            console.error('Error:', error);
          }
        }
        
        fetchMultipleData();

### Promise.race

Si quieres que se resuelva la primera promesa que se complete, puedes usar Promise.race:

        async function fetchFirstData() {
          try {
            const data = await Promise.race([
              fetch('/api/data1').then(response => response.json()),
              fetch('/api/data2').then(response => response.json())
            ]);
            console.log('Primeros datos recibidos:', data);
          } catch (error) {
            console.error('Error:', error);
          }
        }
        
        fetchFirstData();
        
### Promise.allSettled

Si quieres esperar a que todas las promesas se completen, sin importar si se resuelven o rechazan, puedes usar Promise.allSettled:

        async function fetchAllData() {
          const results = await Promise.allSettled([
            fetch('/api/data1').then(response => response.json()),
            fetch('/api/data2').then(response => response.json())
          ]);
        
          results.forEach((result, index) => {
            if (result.status === 'fulfilled') {
              console.log(`Datos ${index + 1} recibidos:`, result.value);
            } else {
              console.error(`Error en datos ${index + 1}:`, result.reason);
            }
          });
        }
        
        fetchAllData();



