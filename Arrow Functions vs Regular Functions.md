### Arguments
  const print = () => {
    console.log(arguments)
  }
  
  print("hello", 400, false)
  // Uncaught ReferenceError: arguments is not defined
