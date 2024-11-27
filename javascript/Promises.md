
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



