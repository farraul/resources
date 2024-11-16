
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
    
## Omit (2)

Type alias can easily use utility types - interface can too but only with ugly syntax

**Type**

        type UserProps = {
          name: string;
          age: number;
          createdAt: Date;   
        
        };
        
        type GuestProps = Omit<UserProps, "name">;

**Interface**

        interface GuestProps extends Omit<UserProps, "name" | "age"> {}



## Tuples (2)

* type alias can easily describe tuples - interface can too but only with ugly syntax

**Type**

        type Address = [number, string];
        
        const address: Address = [2, "Other St."];
        
**Interface**

         


## Extracting
### Normal
Extracting type from something else

    const project = {
      title: "Project 1",
      specification: {
        areaSize: 100,
        rooms: 3,
      },
    };
    
    type Specification = typeof project["specification"];

    console.log(Specification) 
    //type Specification = {
    //      areaSize: number;
          rooms: number;
    //};

### Const

    const project = {
      title: "Project 1",
      specification: {
        areaSize: 100,
        rooms: 3,
      },
    } as const;

    type Specification = typeof project["specification"];

    console.log(Specification) 
    //type Specification = {
    //    readonly  areaSize: 100;
    //    readonly  rooms: 3;
    //};

    

## Declar cualquier tipo de datos (solo type)
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

**Type: creating string**
    
    type Address = string;
    const address: Address = "123 Main St";
    
**Interface: creating object**
 
    interface UserProps {
      name: string;
      age: number;
    };
    
    export default function User({}): UserProps {
      return <div>Card</div>;
    }



## Unión (solo type)

    Type Address = string | string[];
    
    const address: Address = ["123 Main St", "456 North"];
    
## Reference
    https://www.youtube.com/watch?v=Idf0zh9f3qQ

