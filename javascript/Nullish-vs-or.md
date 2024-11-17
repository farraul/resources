## Operador OR (||)
### ¿Cuándo se usa?
* Para proporcionar un valor por defecto cuando cualquier valor es "falsy".
* Para simplificar condiciones lógicas.
  
### ¿Qué valores son "falsy"?
null, undefined, 0, NaN, "", false.

    
        let nombre = null;
        let saludo = nombre || "Invitado";

## Operador nulo (??) (Nullish Coalescing)
### ¿Cuándo se usa?
* Para proporcionar un valor por defecto solo cuando el valor es null o undefined.
  
Ejemplo:

        
        let edad = 0;
        let edadDefecto = edad ?? 30; // edadDefecto será 0 porque edad no es null ni undefined
