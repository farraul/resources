https://dev.to/hriztam/arrow-functions-vs-normal-functions-in-javascript-2l70#:~:text=Normal%20functions%20have%20access%20to,have%20their%20own%20arguments%20object.

## This

#### Regular Function
      const persona = {
    	nombre: 'Agustin',
    	decirNombre(){
    		console.log(this.name)
    	}
     }   
     
    console.log(persona.decirNombre()) // OUTPUT : 'Agustin'
#### Arrow function
##### Ejemplo 1 (error)
      const persona = {
    	nombre: 'Agustin',
    	
    	decirNombre: function() {
    		console.log(this.nombre)
    	}
    	
    	decirNombreFuncionFlecha: () => {
    		console.log(this.nombre)
    	}
     
    }
     
    persona.decirNombreFuncionFlecha(); // OUTPUT : undefined

##### Ejemplo 2 (good)
    const persona = {
    	nombre: 'Agustin',
    	
    	decirNombre: function() {
    		setTimeout(() => {
    			console.log(this.nombre);
    		},
    		3000);
    	}  
    }
    persona.decirNombre(); // OUTPUT : Agustin


  ## Arguments

  ### Regular Function
  
      function displayArguments() {
       console.log(arguments);
      }
      
      displayArguments(1, "hello", true); // Outputs: [1, "hello", true]

### Arrow function

      const displayArguments = () => {
        console.log(arguments); // ReferenceError: arguments is not defined
      }
      
      displayArguments(1, "hello", true);
