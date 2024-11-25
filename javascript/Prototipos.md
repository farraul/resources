En javascript todo son objetos


## 2 formas de asignar
### 1º

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

    sacha.__proto__ = cheff;

### 2º
