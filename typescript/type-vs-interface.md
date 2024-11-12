## Declar objetos
Se puede declar objetos tanto con type como con props

    type UserProps = {
      name: string;
      age: number;
    };
    
    interface UserProps {
      name: string;
      age: number;
    };
    
    export default function User({}): UserProps {
      return <div>Card</div>;
    }

**Pero otro tipo no**
