## Declar cualquier tipo de datos (type)
* Interfaces: solo pueden describir objetos. 

* Type: pueden describir objetos Y cualquier otra cosa (por ejemplo, valores primitivos como string, number, boolean).


**Type: creating object**

    type UserProps = {
      name: string;
      age: number;
    };
    
    export default function User({}): UserProps {
      return <div>Card</div>;
    }
    
**Interface: creating object**
 
    interface UserProps {
      name: string;
      age: number;
    };
    
    export default function User({}): UserProps {
      return <div>Card</div>;
    }


## Extensión (2)

**Type**

        type UserProps = {
          name: string;
          age: number;
        };
        
        type AdminProps = UserProps & {
          role: string;
        };

**Interface**

    interface UserProps {
      name: string;
      age: number;
    }
    
    interface AdminProps extends UserProps {
      role: string;
    }

   ## Reference
    https://www.youtube.com/watch?v=Idf0zh9f3qQ
