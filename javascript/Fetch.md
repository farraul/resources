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
