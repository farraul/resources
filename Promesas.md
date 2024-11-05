
    
### Example 1 
    let promise = new Promise(function(resolve, reject) {
      setTimeout(() => resolve("hecho!"), 1000);
    });
    
    // resolve ejecuta la primera función en .then
    promise.then(
      result => alert(result), // muestra "hecho!" después de 1 segundo
      error => alert(error) // no se ejecuta
    );
