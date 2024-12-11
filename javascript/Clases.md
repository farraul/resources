## Propiedad & método
    const cancion = {
        nombre: 'Aquí todo esta bien', // propiedad
        duracion: 3.02, // propiedad
        añadirAFav: () => { // método
            console.log("La canción se añadió a favoritos"); 
        }
    };

## Explanation


### 1. Clases
Una clase es una plantilla para crear objetos. Define un conjunto de propiedades y métodos que los objetos creados a partir de la clase tendrán.

Ejemplo en JavaScript:

    class Persona {
      constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
      }
    
      saludar() {
        console.log(`Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
      }
    }
    
    const persona1 = new Persona('Juan', 30);
    persona1.saludar(); // Hola, mi nombre es Juan y tengo 30 años.


### 2. Sintaxis básica de clases
La sintaxis básica de una clase incluye la declaración de la clase, el constructor y los métodos.

Ejemplo en JavaScript:

    class Animal {
      constructor(nombre) {
        this.nombre = nombre;
      }
    
      hacerSonido() {
        console.log(`${this.nombre} hace un sonido.`);
      }
    }
    
    const animal = new Animal('Perro');
    animal.hacerSonido(); // Perro hace un sonido.

### 3. Herencia de clases

La herencia permite crear una nueva clase basada en una clase existente, heredando sus propiedades y métodos. El uso de super() en el constructor de la subclase llama al constructor de la superclase.

Ejemplo en JavaScript:

    class Animal {
      constructor(nombre) {
        this.nombre = nombre;
      }
    
      hacerSonido() {
        console.log(`${this.nombre} hace un sonido.`);
      }
    }
    
    class Perro extends Animal {
      constructor(nombre, raza) {
        super(nombre); // Llama al constructor de la superclase (Animal)
        this.raza = raza;
      }
    
      ladrar() {
        console.log(`${this.nombre} ladra.`);
      }
    }
    
    const perro = new Perro('Rex', 'Labrador');
    perro.hacerSonido(); // Rex hace un sonido.
    perro.ladrar(); // Rex ladra.

O también se puede así:

    class Animal {
      constructor(nombre) {
        this.nombre = nombre;
      }
    
      hacerSonido() {
        console.log(`${this.nombre} hace un sonido.`);
      }
    }
    
    class Perro extends Animal {
      ladrar() {
        console.log(`${this.nombre} ladra.`);
      }
    }
    
    const perro = new Perro('Rex');
    perro.hacerSonido(); // Rex hace un sonido.
    perro.ladrar(); // Rex ladra.

### Diferencias Clave
Constructor en la Subclase:

* Primer Fragmento: La clase Perro tiene su propio constructor que acepta dos parámetros (nombre y raza). Dentro de este constructor, se llama a super(nombre) para invocar el constructor de la clase base (Animal) y asignar el valor de nombre. Además, se asigna el valor de raza a la propiedad raza de Perro.
* Segundo Fragmento: La clase Perro no tiene su propio constructor. En este caso, el constructor de la clase base (Animal) se utiliza automáticamente cuando se crea una instancia de Perro.
  
Propiedades Adicionales:

* Primer Fragmento: Perro tiene una propiedad adicional raza, que se inicializa en su constructor.
* Segundo Fragmento: Perro no tiene propiedades adicionales y solo hereda la propiedad nombre de Animal.
* 
Uso de super():

* Primer Fragmento: super(nombre) se utiliza en el constructor de Perro para llamar al constructor de Animal. Esto es necesario cuando la subclase tiene su propio constructor y necesita inicializar la parte heredada de la clase base.
* Segundo Fragmento: No se usa super() porque no hay un constructor en la subclase Perro.
  
### ¿Por qué funcionan ambos?

Ambos fragmentos funcionan porque JavaScript permite que una subclase herede de una superclase sin necesidad de definir un constructor en la subclase. Si no se define un constructor en la subclase, el constructor de la superclase se utiliza automáticamente. Sin embargo, si se define un constructor en la subclase, es necesario llamar a super() para asegurarse de que la parte heredada de la clase base se inicialice correctamente.

### 4. Propiedades y métodos estáticos

Los métodos y propiedades estáticos pertenecen a la clase en sí, no a las instancias de la clase.

Ejemplo en JavaScript:

    class Matematica {
      static sumar(a, b) {
        return a + b;
      }
    }
    
    console.log(Matematica.sumar(5, 3)); // 8
    
### 5. Propiedades y métodos privados y protegidos
Las propiedades y métodos privados solo son accesibles dentro de la clase. Los protegidos son accesibles dentro de la clase y sus subclases.
    
    Ejemplo en JavaScript:
    
    class Persona {
      #edad; // Propiedad privada
    
      constructor(nombre, edad) {
        this.nombre = nombre;
        this.#edad = edad;
      }
    
      obtenerEdad() {
        return this.#edad;
      }
    }
    
    const persona = new Persona('Ana', 25);
    console.log(persona.obtenerEdad()); // 25
    console.log(persona.#edad); // Error: propiedad privada

###  6. Extender clases integradas

Puedes extender clases integradas como Array, Map, etc., para añadir funcionalidades adicionales.

Ejemplo en JavaScript:

    class MiArray extends Array {
      esVacio() {
        return this.length === 0;
      }
    }
    
    const arr = new MiArray(1, 2, 3);
    console.log(arr.esVacio()); // false
    7. Verificación de clases: instanceof
    El operador instanceof se usa para verificar si un objeto es una instancia de una clase específica.
    
    Ejemplo en JavaScript:
    
    class Animal {}
    class Perro extends Animal {}
    
    const perro = new Perro();
    console.log(perro instanceof Perro); // true
    console.log(perro instanceof Animal); // true
    console.log(perro instanceof Object); // true

###  8. Mixins

Los mixins son una forma de añadir funcionalidades a las clases sin usar la herencia.

Ejemplo en JavaScript:

    let mixinSaludo = {
      saludar() {
        console.log(`Hola, soy ${this.nombre}`);
      }
    };
    
    class Persona {
      constructor(nombre) {
        this.nombre = nombre;
      }
    }
    
    Object.assign(Persona.prototype, mixinSaludo);
    
    const persona = new Persona('Carlos');
    persona.saludar(); // Hola, soy Carlos




## Ejemplo

    class Persona {
        constructor(nombre, edad, mujer, direccion) {
            this.nombre = nombre;
            this.edad = edad;
            this.mujer = mujer;
            this.direccion = direccion;   
    
        }
    }
    
    class Alumno extends Persona {
        constructor(nombre, edad, mujer, direccion, matricula, carrera) {
            super(nombre, edad, mujer, direccion); //Estos se meten en super porque vienen del padre
            this.matricula = matricula;
            this.carrera = carrera;
        }
    }
    
    class Maestro extends Persona {
        constructor(nombre, edad, mujer, direccion, materias) {
            super(nombre, edad, mujer, direccion);
            this.materias = materias;
        }
    }
    
    const maestro = new Maestro('Diego', 20, false, 'XXXXXXXXX', ['Matematicas', 'Fisica', 'Quimica']);
    const alumno = new Alumno('Abril', 14, true, 'YYYYYYYY', '2020405067', 'Tec. en Programación');
