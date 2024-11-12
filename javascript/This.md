## Contexto Global 
En el contexto global (fuera de cualquier función), this se refiere al objeto global, que es window en navegadores web.

    console.log(this); // En un navegador, esto imprimirá el objeto `window`


## Dentro de una Función
En una función, el valor de this depende de cómo se llama a la función.

    function mostrar() {
        console.log(this);
    }
    mostrar(); // En modo no estricto, `this` será el objeto global (window en navegadores)


## Métodos de un Objeto 
Cuando this se usa dentro de un método de un objeto, se refiere al objeto al que pertenece el método.

    const persona = {
        nombre: 'Juan',
        saludar: function() {
            console.log('Hola, soy ' + this.nombre);
        }
    };
    persona.saludar(); // 'Hola, soy Juan'
    
## Constructores 
En una función constructora, this se refiere al nuevo objeto que se está creando.

    function Persona(nombre) {
        this.nombre = nombre;
    }
    const juan = new Persona('Juan');
    console.log(juan.nombre); // 'Juan'

## Enlace Explícito 
Puedes usar call, apply o bind para establecer explícitamente el valor de this.

    function saludar() {
        console.log('Hola, soy ' + this.nombre);
    }
    const persona = { nombre: 'Ana' };
    saludar.call(persona); // 'Hola, soy Ana'

## Funciones Flecha
Las funciones flecha no tienen su propio this. En su lugar, heredan this del contexto en el que fueron definidas.

    const persona = {
        nombre: 'Carlos',
        saludar: function() {
            const mostrarNombre = () => {
                console.log('Hola, soy ' + this.nombre);
            };
            mostrarNombre();
        }
    };
    persona.saludar(); // 'Hola, soy Carlos'
