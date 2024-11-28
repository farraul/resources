Las funciones que operan en otras funciones, ya sea tomándolas como argumentos o retornandolas, se denominan funciones de orden superior.


    function mayorQue(n) {
      return m => m > n;
    }
    let mayorQue10 = mayorQue(10);
    console.log(mayorQue10(11));
    // → true

Y puedes tener funciones que cambien otras funciones.


    function ruidosa(funcion) {
      return (...argumentos) => {
        console.log("llamando con", argumentos);
        let resultado = funcion(...argumentos);
        console.log("llamada con", argumentos, ", retorno", resultado);
        
        return resultado;
      };
    }
    
    ruidosa(Math.min)(3, 2, 1);
    // → llamando con [3, 2, 1]
    // → llamada con [3, 2, 1] , retorno 1
