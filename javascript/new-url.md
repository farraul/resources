* Protocolo: Indica el protocolo utilizado para acceder al recurso (HTTP o HTTPS en este caso).
* Host: El nombre de dominio completo (incluyendo el puerto si está especificado).
* Hostname: Solo el nombre de dominio sin el puerto.
* Puerto: El número de puerto utilizado. Si no se especifica, se omite en la salida.
* Path: La ruta al recurso dentro del servidor web.
* Query string: La cadena de consulta que contiene parámetros adicionales.
* Parámetros de la query: Un objeto que representa los parámetros de la query y sus valores.
* Fragmento: La parte de la URL después del símbolo #, que se utiliza para identificar una sección específica de un documento.

      let urlString = 'https://www.example.com/path/to/file?param1=value1&param2=value2#fragment';
      let url = new URL(urlString);
      
      console.log('URL completa:', url.href);
      // Salida: https://www.example.com/path/to/file?param1=value1&param2=value2#fragment
      
      console.log('Protocolo:', url.protocol);
      // Salida: https:
      
      console.log('Host:', url.host);
      // Salida: www.example.com
      
      console.log('Hostname:', url.hostname);
      // Salida: www.example.com
      
      console.log('Puerto:', url.port);
      // Salida: 
      
      console.log('Path:', url.pathname);
      // Salida: /path/to/file
      
      console.log('Query string:', url.search);
      // Salida: ?param1=value1&param2=value2
      
      console.log('Parámetros de la query:', url.searchParams);
      // Salida: URLSearchParams { param1: 'value1', param2: 'value2' }
      
      console.log('Fragmento:', url.hash);
      // Salida: #fragment
