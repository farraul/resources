## Throw new error
	try{  
	     throw new Error('Transfer failed');
	  }catch(error){
	    console.log("error", error)
	    console.log("Error name:", error.name);
	    console.log("Error message:", error.message);
	    console.log("Error stack (if available):", error.stack); 
	  }

![image](https://github.com/user-attachments/assets/8bd64a52-e307-4e38-a592-1db9390e0e9b)

## Throw
	  try{  
	     throw('Transfer failed');
	  }catch(error){
	    console.log("error", error);
	    console.log("Error name:", error.name);
	    console.log("Error message:", error.message);
	    console.log("Error stack (if available):", error.stack); 
	  }
![image](https://github.com/user-attachments/assets/d6f46f8a-af5d-4846-b596-943e12cf751f)



## ¿Cuándo usar cada un Throw new error y cuando Throw?


### throw new Error():

* Generalmente: Es la opción preferida para lanzar excepciones, ya que proporciona más información y facilita la depuración.
####  Casos de uso:
* Cuando necesitas crear errores personalizados con mensajes específicos.
* Cuando quieres aprovechar las propiedades de los objetos Error (como stack).

### throw:

#### Casos específicos:
* Cuando necesitas lanzar valores personalizados que no son necesariamente errores (por ejemplo, un objeto que representa un estado de error).
* En situaciones donde la simplicidad es prioritaria y no necesitas mucha información sobre el error.

## HandleError (Utils)

    import toast from "react-hot-toast";
    export const handleError = (error: unknown) => {
      let message;
    
      if (error instanceof Error) {
        message = error.message;
      } else if (typeof error === "string") {
        message = error;
      } else {
        message = "An error occurred.";
      }
    
      toast.error(message);
    };


## Errores ejemplos
### Ejemplo 1
#### File1.jsx

	export class ConnectionError extends Error {
	    constructor(message) {
	        super(message);
	        this.name = 'ConnectionError';
	    }
	}
	
	export class ValidationError extends Error {
	    constructor(message) {
	        super(message);
	        this.name = 'ValidationError';   
	
	    }
	}

#### File2.jsx

	const validateUser = ({ name, age, email } = {}) => {
	  if (!name) throw new ValidationError('name is required');
	  if (!age) throw new ValidationError('age is required');   	
	  if (!email) throw new ValidationError('email is required');
	}

 
 #### File3.jsx
	
	import { ValidationFromError, ConnectionInfoError } from './errors.js';
	import { validateUser } from './validations.js';
	
	const name = 'midu';
	const age = 30;
	const email = '';
	
	try {
	  validateUser(name, age, email);
	} catch (e) {
	  if (e instanceof ConnectionError) {
	    // retry after a few seconds
	    setTimeout(() => {
	      validateUser(name, age, email);
	    }, 2000);
	  }
	
	  if (e instanceof ValidationError) {
	    // showUIModalValidation()
	  }
	}
 
 ### Ejemplo 2
	 
	class TokenError extends Error {
	 metadata;
	
	  constructor(message, metadata) {
	    super(message);
	    this.metadata = metadata;
	  }
	}
	
	function run(url) {
	  const apiURL = new URL(url);
	  const params = apiURL.searchParams;
	  const token = params.get("token");
	
	  if (!token ||  token !== 'maluma123') {
	    throw new TokenError("Token no existe", {
	     token,
	     url
	    });
	  }
	
	  console.log({ token });
	}
	
	function catchError() {
	 try {
	  run("https://myapi.com?token=badbunny123");
	 } catch (error) {
	    if (error instanceof TypeError) {
	      console.log("La URL que ingresaste no es válida");
	    } else if (error instanceof TokenError) {
	      console.log("La URL no tiene un param de token", error.metadata);
	    }
	  }
	}
	
	catchError();




### Ejemplo 3

    const NUM_PIEZAS = 5;
    const PROB_ERROR = 0.25;
    let correctas = 0;
    let defectuosas = 0;
    
    const comprobarSiEsDefectuosa = () => Math.random() < PROB_ERROR;
    
    class ErrorPiezaDefectuosa extends Error {}
    class ErrorCadenaParada extends Error {}
    
    for (let i = 1; i <= NUM_PIEZAS; i++) {
        const esDefectuosa = comprobarSiEsDefectuosa();
    
        try {
            if (i === 2) throw new ErrorCadenaParada("Se paró");
            if (esDefectuosa) throw new ErrorPiezaDefectuosa("Pieza defectuosa");
        } catch (ex) {
            correctas++;
            if (ex instanceof ErrorCadenaParada) {
                console.log("Se ha parado la cadena");
                throw ex;
            }
            if (ex instanceof ErrorPiezaDefectuosa) {
                console.log(`La pieza ${i} es defectuosa`);
                }
            defectuosas++;
        }
    }
    
    console.log(`Fabricadas: ${NUM_PIEZAS}`);
    console.log(`Correctas: ${correctas}`);
    console.log(`Defectuosas: ${defectuosas}`); 

## Creador de errores

	const createErrorFactory = function(name) {
	  return class BusinessError extends Error {
		constructor(message) {
		  super(message);
		  this.name = 'ConnectionError'; // Aquí está el problema
		}
	  };
	};

	export const ConnectionError = createErrorFactory('ConnectionError');
	export const ValidationError = createErrorFactory('ValidationError');



