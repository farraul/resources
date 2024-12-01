### Push
Adds one or more elements to the end of an array.

    const numbers = [1, 2, 3];
    numbers.push(4, 5); // numbers is now [1, 2, 3, 4, 5]


### Pop
Removes the last element from an array.

    const fruits = ["apple", "banana", "cherry"];
    const removedFruit = fruits.pop(); // removedFruit is "cherry", fruits is ["apple", "banana"]


### Unshift
Adds one or more elements to the beginning of an array.

    const animals = ["cat", "dog"];
    animals.unshift("bird", "fish"); // animals is now ["bird", "fish", "cat", "dog"]

### Slice
Extracts a section of an array and returns a new array.

    const numbers = [10, 20, 30, 40, 50];
    const slicedNumbers = numbers.slice(1, 4); // slicedNumbers is [20, 30, 40]

### Splice
Removes or replaces elements from an array and optionally inserts new elements.

    const letters = ["a", "b", "c", "d"];
    letters.splice(2, 1, "x", "y"); // letters is now ["a", "b", "x", "y", "d"]

### Concat
Merges two or more arrays, returning a new array.

    const array1 = [1, 2];
    const array2 = [3, 4, 5];
    const mergedArray = array1.concat(array2); // mergedArray is [1, 2, 3, 4, 5]

### Join
Joins all elements of an array into a string, using a specified separator.

    const words = ["hello", "world"];
    const joinedString = words.join(" "); // joinedString is "hello world"

### ForEach
Executes a provided function once for each array element.

    const numbers = [1, 2, 3];
    numbers.forEach(number => console.log(number)); // Logs 1, 2, 3 to the console

### Map

Creates a new array by transforming each element of the original array.

    const numbers = [1, 2, 3];
    const doubledNumbers = numbers.map(number => number * 2); // doubledNumbers is [2, 4, 6]

### Filter
Creates a new array containing only elements that pass a test implemented by a provided function.

    const numbers = [1, 2, 3, 4, 5];
    const evenNumbers = numbers.filter(number => number % 2 === 0); // evenNumbers is [2, 4]


### Reduce
Reduces an array to a single value by applying a function to each element and accumulating the result.
    
    const numbers = [1, 2, 3];
    const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0); // sum is 6
