En javascript todo son objetos


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
