## Fetch
Fetch es una promesa
### Usando .then

    fetch('/api/data')
      .then(response => response.json())
      .then(data => {
        console.log('Datos recibidos:', data);
      })
      .catch(error => {
        console.error('Error:', error);
      });
  

  ## Usando async/await

    async function fetchData() {
        try {
            const response = await fetch('/api/data');
            const data = await response.json();
            console.log('Datos recibidos:', data);
        } catch (error) {
            console.error('Error:', error);
        }
    }
    
    fetchData();


## Ejemplo implementando el metodo POST:

        async function postData(url = '', data = {}) {
        
          // Opciones por defecto estan marcadas con un *
          
          const response = await fetch(url, {
            method: 'POST', // *GET, POST, PUT, DELETE, etc.
            mode: 'cors', // no-cors, *cors, same-origin
            cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
            credentials: 'same-origin', // include, *same-origin, omit
            headers: {
              'Content-Type': 'application/json'
              // 'Content-Type': 'application/x-www-form-urlencoded',
            },
            redirect: 'follow', // manual, *follow, error
            referrerPolicy: 'no-referrer', // no-referrer, *no-referrer-when-downgrade, origin, origin-when-cross-origin, same-origin, strict-origin, strict-origin-when-cross-origin, unsafe-url
            body: JSON.stringify(data) // body data type must match "Content-Type" header
          });
          
          return response.json(); // parses JSON response into native JavaScript objects
        }
        
        postData('https://example.com/answer', { answer: 42 })
          .then(data => {
            console.log(data); // JSON data parsed by `data.json()` call
          });
