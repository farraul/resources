# ¿Qué son estos métodos call, apply y bind?
Para decirlo de una manera simple, todos estos métodos se usan para cambiar el valor de this dentro de una función.


## Bind
Con el método bind podemos garantizar que un método siempre se invoque en un contexto específico.
    let greet = function() {
      console.log(`Hola ${this.name}`)
    }
    
    const pedro = { name: "Pedro" }
    greet = greet.bind(pedro); // sobrescribimos la variable
    
    greet() // "Hola Pedro"

El método bind devuelve una nueva función que encapsula a la original para garantizar que siempre se ejecute con el contexto que queremos. En este ejemplo estamos sobrescribiendo la variable greet pero hubiésemos podido asignarla a una variable diferente.



## call y apply
Estos dos métodos nos permiten cambiar el contexto del this al invocar una función. Por ejemplo, imagina que tenemos una función llamada greet que utiliza this internamente, podemos utilizar call para cambiar el contexto de this al invocarla:

      const greet = function() {
        console.log(`Hola ${this.name}`)
      }
      
      const pedro = { name: "Pedro" }
      greet.call(pedro) // "Hola Pedro"
      
      const maria = { name: "Maria" }
      greet.call(maria) // "Hola Maria"

La diferencia entre call y apply es la forma en que se pasan los argumentos de la función: apply recibe los argumentos como un arreglo, mientras que call los recibe como argumentos independientes.

    const sum = function(a, b) {
      console.log(`${this.name}, el resultado es ${a + b}`)
    }
    
    const pedro = { name: "Pedro" }
    sum.call(pedro, 1, 2) // "Pedro, el resultado es 3"
    sum.apply(pedro, [1, 2]) // "Pedro, el resultado es 3"

