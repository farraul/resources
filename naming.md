
## Types
* kebab-case
* snake_case
* CamelCase


## Magic numbers
    let dollarsPerEuro = 1.25;
    let dollarsCount = 50 * dollarsPerEuro; // dollarsPerEuro es un Magic numbers
    
## Interpolation

    const firstName = 'Joffrey';
    const greeting = 'Hello';
    
    console.log(greeting + ', ' + firstName + '!');
    // => 'Hello, Joffrey!'



## To components el "handle se quita y se pone on"


      const handleClick = () => {
        setContador(contador + 1);
      };
    
      return (
        <div>
          <p>Has hecho clic {contador} veces.</p>
          <button onClick={handleClick}>Haz clic aquí</button>
        </div>
      );
    }

**Example 2**

        const handleNavigate= {...}
        return(<Controller onNavigate={handleNavigate}/)


##  Naming Convention for Variables

    const dogName = 'Droopy';
    const userInfo = {...}
    
## Naming Convention for Booleans

    let hasOwner = true;
    let isTrained = false;

## Naming Convention for Functions

    function getName(dogName, ownerName) { 
      return '${dogName} ${ownerName}';
    }
   
    
    function calculateDogAgeInHumanYears(dogAge) {
      return dogAge * 7;
    }

## Naming Convention for Constants
    const DAYS_IN_WEEK = 7;
## Naming Convention for Global Variables
    const GLOBAL_MAX_COUNT = 100;

