Las propiedades de acceso se construyen con métodos de obtención “getter” y asignación “setter”. En un objeto literal se denotan con get y set:

    let obj = {
      get propName() {
        // getter, el código ejecutado para obtener obj.propName
      },
    
      set propName(value) {
        // setter, el código ejecutado para asignar obj.propName = value
      }
    };

## Getters y setters más inteligentes

Getters y setters pueden ser usados como envoltorios sobre valores de propiedad “reales” para obtener más control sobre ellos.

Por ejemplo, si queremos prohibir nombres demasiado cortos para “usuario”, podemos guardar “nombre” en una propiedad especial “nombre”. Y filtrar las asignaciones en el setter:

    let user = {
      get name() {
        return this._name;
      },
    
      set name(value) {
        if (value.length < 4) {
          alert("El nombre es demasiado corto, necesita al menos 4 caracteres");
          return;
        }
        this._name = value;
      }
    };
    
    user.name = "Pete";
    alert(user.name); // Pete
    
    user.name = ""; // El nombre es demasiado corto...
