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
