
## JSON.parse()
* Función: Toma una cadena de texto en formato JSON y la convierte en un objeto de JavaScript.
  
 Ejemplo:

    const cadenaJSON = '{"nombre": "Alicia", "edad": 30}';
    const objetoJS = JSON.parse(cadenaJSON);
    console.log(objetoJS.nombre); // Imprime: Alicia

## JSON.stringify()

* Función: Convierte un objeto de JavaScript en una cadena de texto en formato JSON.

Ejemplo:

    const objetoJS = { nombre: "Bob", edad: 25 };
    const cadenaJSON = JSON.stringify(objetoJS);
    console.log(cadenaJSON); // Imprime: {"nombre":"Bob","edad":25}
    Usa el código con precaución.

## res.json()
* Función: Para realizar una solicitud desde el front-end y recibir una respuesta en formato JSON,

Ejemplo:

       fetch('/usuarios').then(response => response.json())

