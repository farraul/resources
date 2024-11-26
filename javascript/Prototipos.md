En javascript todo son objetos mientras no sean primitivos.


## 2 formas de asignar
Hacer esto no es aconsejable pero esto es para un fin educativo.

    const cheff = {
      tipo: 'Cocina Básica',
      cocinar: function (plato) {
        console.log('Cocinando ${plato}');
      }
    };
    
    const sacha = {
      nombre: 'Sacha',
      edad: 31,
      profesion: 'Developer'
    };

### 1º
    sacha.__proto__ = cheff;

### 2º
    Object.setPrototypeOf(sacha, cheff);

Por lo tanto ahora tenemos acceso:

![image](https://github.com/user-attachments/assets/18e570d2-7eb9-4f13-924a-25eda1543702)


Primero se fija en el objeto (sacha) y después en el prototipo/s (cheff).

### Todo lo que no sea primitvo tiene prototipos
Ejemplos:

        const pepe = { nombre: 'Pepe' };
        const numeros = [3, 57, 94];
        const sumar = (a, b) => a + b;
        const regexp = /\d+/gi;
        const ahora = new Date();

### Object.prototype
Tiene todos estos métodos:

![image](https://github.com/user-attachments/assets/98f894a8-6d54-463c-8ca3-a95dde4f1235)

### Comprobamos que son iguales los métodos que tiene el Object que el que tiene los objetos

![image](https://github.com/user-attachments/assets/e3989088-79c5-483e-8026-d5ddf88e179f)

### Ver métodos

![image](https://github.com/user-attachments/assets/b1f81c5a-2bab-4c60-8a3e-a0623d098aac)

### Todos salen de object
![image](https://github.com/user-attachments/assets/dcc0ef39-2376-4d45-950e-1445a3e6ec86)

### This

        const cheff = {
          tipo: 'Cocina Básica',
          cocinar: function(plato) {
            console.log('Cocinando ' + plato);
          },
          presentarse: function() {
            console.log('Hola, soy un cheff especializado en ' + this.tipo);
          }
        };
        
        const sacha = {
          nombre: 'Sacha',
          edad: 31,
          profesion: 'Developer',
          tipo: 'Front-End'
        };

![image](https://github.com/user-attachments/assets/ac48636b-fa80-4814-ab1e-737a0fef5703)



### Crear 
Le pasamos el ptototipo y nos devuelve un nuevo objeto

        const sacha = Object.create(cheff);


        function Cheff(tipo = 'cocina básica') {
  this.tipo = tipo;
}


## Funciones constructoras y clases

        function Cheff(tipo = 'cocina básica') {
          this.tipo = tipo;
        }
        
        Cheff.prototype.cocinar = function(plato) {
          console.log('Cocinando ' + plato);
        };
        
        Cheff.prototype.presentarse = function() {
          console.log('Hola, soy un cheff especializado');
        }
        
        const sacha = new Cheff();

 Y desde ECMAscript 15 se puede poner class en vez de function:
 
         class Cheff(tipo = 'cocina básica') {
          this.tipo = tipo;
        }
        
        Cheff.prototype.cocinar = function(plato) {
          console.log('Cocinando ' + plato);
        };
        
        Cheff.prototype.presentarse = function() {
          console.log('Hola, soy un cheff especializado');
        }
        
        const sacha = new Cheff();
        
## Reference
https://www.youtube.com/watch?v=a2tp64Vtzxs
