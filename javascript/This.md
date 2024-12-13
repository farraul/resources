## Contexto Global 
En el contexto global (fuera de cualquier función), this se refiere al objeto global, que es window en navegadores web.

    console.log(this); // En un navegador, esto imprimirá el objeto `window`


## Dentro de una Función
En una función, el valor de this depende de cómo se llama a la función.

    function funcion() {
        console.log(this);
    }
    funcion(); // window

#### use strict
      "use strict";
    function funcion() {
        console.log(this);
    }
    funcion(); // undefined

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

## Ejemplo

    function foo() {
      this.a = 2;
    }
    
    const obj = {
      foo: foo
    };
    
    obj.foo();
    console.log(obj.a); // 2



## Ejemplo 2
    function Point2D(x, y) {
    this.x = x;
    this.y = y;
    }
    
    const p1 = new Point2D(1, 2);
    console.log(p1.x); // 1
    console.log(p1.y); // 2
