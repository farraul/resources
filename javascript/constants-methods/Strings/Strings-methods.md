### toUpperCase y toLowerCase
Convierten todos los caracteres de una cadena a mayúsculas o minúsculas, respectivamente.

    let texto = "Hola, Mundo";
    let textoMayusculas = texto.toUpperCase(); // "HOLA, MUNDO"
    let textoMinusculas = texto.toLowerCase(); // "hola, mundo"


### IndexOf y lastIndexOf
 Encuentran la primera o última ocurrencia de un substring dentro de una cadena, devolviendo el índice de la posición.
 
    let saludo = "Hola, ¿cómo estás?";
    let indiceComa = saludo.indexOf(","); // 4
    let indiceUltimaO = saludo.lastIndexOf("o"); // 15


### Slice
Extrae una porción de una cadena y devuelve una nueva cadena.

    let palabra = "JavaScript";
    let subcadena = palabra.slice(4, 10); // "Script"


### substring
Similar a slice(), pero los índices negativos no son permitidos.

### Replace()
Reemplaza todas las ocurrencias de un substring con otro.

    let texto = "El gato está en el gato";
    let nuevoTexto = texto.replace("gato", "perro"); // "El perro está en el gato"


### split
Divide una cadena en un array de substrings, basado en un separador.

    let nombres = "Juan,María,Pedro";
    let arrayNombres = nombres.split(","); // ["Juan", "María", "Pedro"]


### Concat
Combina dos o más cadenas en una nueva cadena.

    let saludo1 = "Hola";
    let saludo2 = "Mundo";
    let saludoCompleto = saludo1.concat(" ", saludo2); // "Hola Mundo"
