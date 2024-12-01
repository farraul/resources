### Object.assign(target, source)

Copies properties from a source object to a target object

    const target = { a: 1, b: 2 };
    const source = { b: 4, c: 5 };
    
    const result = Object.assign(target, source);
    
    console.log(result); // Output: { a: 1, b: 4, c: 5 }

### Object.create(object)

Creates an object from an existing object. Creates a new object, and sets the __proto__ property of that object to the specified object.

    const person = {
      firstName: "John",
      lastName: "Doe"
    };
    
    const employee = Object.create(person);
    employee.jobTitle = "Software Engineer";
    
    console.log(employee); // Output: { jobTitle: "Software Engineer" }
    console.log(employee.firstName); // Output: "John" (inherited from person)

### Object.entries(object)

Returns an array of the key/value pairs of an object

        const person = { name: "Alice", age: 30 };
        const entries = Object.entries(person);
        
        console.log(entries); // Output: [["name", "Alice"], ["age", 30]]

### Object.fromEntries()

Creates an object from a list of keys/values. Array of arrays to object

        const entries = [["name", "Bob"], ["age", 25]];
        const person = Object.fromEntries(entries);
        
        console.log(person); // Output: { name: "Bob", age: 25 }

### Object.keys(object)

Returns an array of the keys of an object. 
        
        const person = { name: "Alice", age: 30, city: "New York" };
        const keys = Object.keys(person);
        
        console.log(keys); // Output: ["name", "age", "city"]

### Object.values(object)

Returns an array of the property values of an object

        const person = {
          firstName: "John",
          lastName: "Doe",
          age: 30
        };
        
        const values = Object.values(person);
        console.log(values); // Output: ["John", "Doe", 30]

### Object.groupBy(object, callback)

Groups object elements according to a function

        const people = [
          { name: 'Alice', age: 25, city: 'New York' },
          { name: 'Bob', age: 30, city: 'Los Angeles' },
          { name: 'Charlie', age: 25, city: 'Chicago' },
          { name: 'David', age: 30, city: 'New York' }
        ];
        
        const groupedPeopleByAge = Object.groupBy(people, person => person.age);
        console.log(groupedPeopleByAge); // Output: { '25': [{ name: 'Alice', age: 25, city: 'New York' }, { name: 'Charlie', age: 25, city: 'Chicago' }], '30': [{ name: 'Bob', age: 30, city: 'Los Angeles' }, { name: 'David', age: 30, city: 'New York' }] }
