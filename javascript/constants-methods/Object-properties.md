Las propiedades de objeto, aparte de un value, tienen tres atributos especiales (también llamados “indicadores”):

* writable – si es true, puede ser editado, de otra manera es de solo lectura.
* enumerable – si es true, puede ser listado en bucles, de otro modo no puede serlo.
* configurable – si es true, la propiedad puede ser borrada y estos atributos pueden ser modificados, de otra forma no.


      
      const miObjeto = {};
      
      // Creando una propiedad no-escriturable
      Object.defineProperty(miObjeto, 'nombre', {
        value: 'Juan',
        writable: false
      });
      
      // Intentar cambiar el valor (dará error)
      miObjeto.nombre = 'María';
      
      // Creando una propiedad no-enumerable
      Object.defineProperty(miObjeto, 'edad', {
        value: 30,
        enumerable: false
      });
      
      // El bucle for...in no incluirá la propiedad 'edad'
      for (const prop in miObjeto) {
        console.log(prop); // Solo imprimirá 'nombre'
      }
      
      // Creando una propiedad no-configurable
      Object.defineProperty(miObjeto, 'esAdulto', {
        value: true,
        configurable: false
      });
      
      // Intentar hacer la propiedad 'esAdulto' escribible (dará error)
      Object.defineProperty(miObjeto, 'esAdulto', {
        writable: true
      });


### Writable

      const object1 = {};
      
      Object.defineProperty(object1, 'property1', {
        value: 42,
        writable: false,
      });
      
      object1.property1 = 77;
      // Throws an error in strict mode
      
      console.log(object1.property1);
      // Expected output: 42
