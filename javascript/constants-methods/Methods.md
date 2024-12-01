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

### Object.fromEntries()

Creates an object from a list of keys/values. Array of arrays to object

### Object.keys(object)

Returns an array of the keys of an object. 

### Object.values(object)

Returns an array of the property values of an object

### Object.groupBy(object, callback)

Groups object elements according to a function

