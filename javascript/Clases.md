## Propiedad & método
    const cancion = {
        nombre: 'Aquí todo esta bien', // propiedad
        duracion: 3.02, // propiedad
        añadirAFav: () => { // método
            console.log("La canción se añadió a favoritos"); 
        }
    };

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
