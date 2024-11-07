#### TimeOutPromise
    
    const timeOutPromise = (delay) =>  new Promise((resolve, _reject) => { setTimeout(resolve, delay); });
    
    async function exampleUsage() {
        console.log("Starting..."); 
        await timeOutPromise(5000);
        console.log("Two seconds later.."); 
    }
    
    exampleUsage()
