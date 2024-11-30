Las propiedades de objeto, aparte de un value, tienen tres atributos especiales (también llamados “indicadores”):

* writable – si es true, puede ser editado, de otra manera es de solo lectura.
* enumerable – si es true, puede ser listado en bucles, de otro modo no puede serlo.
* configurable – si es true, la propiedad puede ser borrada y estos atributos pueden ser modificados, de otra forma no.

## Object.getOwnPropertyDescriptor(object, key)

      const person = {
         firstName: "John",
         lastName: "Doe"
      };
      
      const firstNameProperty = Object.getOwnPropertyDescriptor(person, "firstName");
      console.log(firstNameProperty);

![image](https://github.com/user-attachments/assets/56a63cbc-3554-48f1-934e-4cd5376e1a34)



## Writable

      Object.defineProperty( newObject, 'a', {
         value: "some value",
         writable: true,
      });
      // Object {a: "some value"}
      
      newObj.a = 'some other new value';
      // "some other new value"
      
      newObj
      // Object {a: "some other new value"}


### Non-writable

      Object.defineProperty( newObject, 'a', {
         value: "some value",
         writable: false,
      });
      // Object {a: "some value"}
      
      newObj.a = 'some other new value';
      // "some other new value"
      
      newObject
      // Object {a: "some value"}

## Enumerable

            Object.defineProperty( newObject, 'a', {
               value: "some value",
               enumerable: true,
            });
            // Object {a: "some value"}
            for (var key in newObject) { console.log(key) }
            // a
            
            Object.keys(newObject);
            // ["a"]


### Non-Enumerable

            Object.defineProperty( newObject, 'a', {
               value: "some value",
               enumerable: false,
            });
            // Object {a: "some value"}
            for (var key in newObject) { console.log(key) }
            // undefined
            Object.keys(newObject);
            // []


## Configurable

      Object.defineProperty( newObject, 'a', {
         value: "some value",
         configurable: true,
      });
      // Object {a: "some value"}
      delete newObject.a;
      // true
      newObject
      // Object {}


### Non-configurable

      Object.defineProperty( newObject, 'a', {
         value: "some value",
         configurable: false,
      });
      // Object {a: "some value"}
      delete newObject.a;
      // false
      newObject
      // Object {a: "some value"}
