### This

#### Regular Function
      const persona = {
    	nombre: 'Agustin',
    	decirNombre(){
    		console.log(this.name)
    	}
     }   
     
    console.log(persona.decirNombre()) // OUTPUT : 'Agustin'
### Arrow function
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


  ### Arguments
