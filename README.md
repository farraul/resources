## useHooks

### useDebounce
    export function useDebounce<T>(value: T, delay = 500): T {
      const [debouncedValue, setDebouncedValue] = useState(value);
    
      useEffect(() => {
        const timerId = setTimeout(() => setDebouncedValue(value), delay);
    
        return () => clearTimeout(timerId);
      }, [value, delay]);
    
      return debouncedValue;
    }

### useLocalStorage
```javascript
export function useLocalStorage<T>(
  key: string,
  initialValue: T
): [T, React.Dispatch<React.SetStateAction<T>>] {
  const [value, setValue] = useState(() =>
    JSON.parse(localStorage.getItem(key) || JSON.stringify(initialValue))
  );

  useEffect(() => {
    localStorage.setItem(key, JSON.stringify(value));
  }, [value, key]);

  return [value, setValue] as const;
}

  const [bookmarkedIds, setBookmarkedIds] = useLocalStorage<number[]>(
    "bookmarkedIds",
    []
  );

```
### useContext
    export function useBookmarksContext() {
      const context = useContext(BookmarksContext);
      if (!context) {
        throw new Error(
          "useBookmarksContext must be used within a BookmarksContextProvider"
        );
      }
      return context;
    }
    
## Utils

### handleError
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

## Errores
Crear error :

	export class ValidationError extends Error {
		constructor(message) {
			super(message);
			this.name = 'ValidationError';   
		}
	}

Creador de errores:

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



Ejemplo 2:

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
            if (i === 2) throw new  ErrorCadenaParada("Se paró");
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

