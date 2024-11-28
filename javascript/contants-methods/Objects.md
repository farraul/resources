# Iterar

### 1. Usando la propiedad Object.keys()

    let perro = {
      nombre: "Scott",
      color: "Negro",
      macho: true,
      edad: 5
    };
    
    let claves = Object.keys(perro); // claves = ["nombre", "color", "macho", "edad"]
    for(let i=0; i< claves.length; i++){
      let clave = claves[i];
      console.log(perro[clave]);
    }
    
    /*
    "Scott"
    "Negro"
    true
    5
    */

### 2. Usando la propiedad Object.values()

    let perro = {
      nombre: "Scott",
      color: "Negro",
      macho: true,
      edad: 5
    };
    
    let valores = Object.values(perro); // valores = ["Scott", "Negro", true, 5];
    for(let i=0; i< valores.length; i++){
      console.log(valores[i]);
    }
    /*
    "Scott"
    "Negro"
    true
    5
    */

### 3. Usando un bucle for...in

    let perro = {
      nombre: "Scott",
      color: "Negro",
      macho: true,
      edad: 5
    };
    
    for (let clave in perro){
      console.log(perro[clave]);
    }
    /*
    "Scott"
    "Negro"
    true
    5
    */


### 4. Usando la propiedad Object.entries() con un forEach()

    let perro = {
      nombre: "Scott",
      color: "Negro",
      macho: true,
      edad: 5
    };
    
    //Object.entries(perro): [["nombre","Scott"],["color","Negro"],["macho",true],["edad",5]]
    
    Object.entries(perro).forEach(([key, value]) => {
      console.log(value)
    });
    
    /*salida:
    "Scott"
    "Negro"
    true
    5
    */
    
### 5.  Usando la propiedad Object.entries() y un bucle for...of

    let perro = {
      nombre: "Scott",
      color: "Negro",
      macho: true,
      edad: 5
    };
    
    for(const [key, value] of Object.entries(perro)){
      console.log(value)
    }
    
    /*salida:
    "Scott"
    "Negro"
    true
    5
    */
