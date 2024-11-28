
## Datos primitivos en JavaScript

JavaScript tiene seis tipos de datos primitivos: string, number, boolean, null, undefinedy symbol. Estos tipos de datos son inmutables, lo que significa que cuando se cambia una variable que contiene un tipo de datos primitivo, se crea una nueva copia del valor. Examinemos un ejemplo:

    sea ​​a = 5 ; 
    sea b = a; 
    
    b = 10 ; 
    
    console . log (a); // Salida: 5 
    console . log (b); // Salida: 10


## Datos complejos en JavaScript: cambios de propiedades

Al trabajar con objetos complejos en JavaScript, al asignarlos a otra variable no se crea una copia sino una referencia al objeto original. Si cambias una propiedad de un objeto a través de una de las variables, la otra variable también se verá afectada. Veamos un ejemplo:
    
    let obj1 = { nombre : "Juan" }; 
    let obj2 = obj1; 
  
    obj2.nombre = "Alicia" ;
    
    console.log ( obj1.nombre ); // Salida: " Alicia " 
    console.log (obj2.nombre ); // Salida : "Alicia"
    obj2 = { nombre : "Sebastián" }; 
    console.log (obj1.nombre ); // Salida: " Alicia" 
    console.log (obj2.nombre ); // Salida: "Sebastián"

### Solución
#### JSON.parse(JSON.stringify()) 

    // Objeto original
    const originalObject = {
      name: "John Doe",
      age: 30,
      address: {
        street: "Main Street",
        city: "Anytown"
      }
    };
    
    // Crear una copia independiente
    const copiedObject = JSON.parse(JSON.stringify(originalObject));
    
    // Modificar el objeto original
    originalObject.name = "Jane Doe";
    
    // Verificar que la copia no se ha modificado
    console.log(copiedObject.name); // Output: John Doe

#### StructuredClone

    const originalObject = {
      name: "John Doe",
      age: 30,
      date: new Date(),
      symbolProp: Symbol('mySymbol')
    };
    
    const copiedObject = structuredClone(originalObject);
    
    // Modificar el objeto original
    originalObject.name = "Jane Doe";
    
    // Verificar que la copia no se ha modificado
    console.log(copiedObject.name); // Output: John Doe
    console.log(copiedObject.date instanceof Date); // Output: true
