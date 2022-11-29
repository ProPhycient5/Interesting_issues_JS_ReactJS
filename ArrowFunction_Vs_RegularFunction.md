- **Arrow function** — also called fat arrow function— is a new feature introduced in ES6 that is a more concise syntax for writing function expressions. 
While both regular JavaScript functions and arrow functions work in a similar manner, there are certain differences between them.
  - It is always an anonymous function.
  - It cannot be invoked before declaration(or definition) because it follows the hoisting pattern of variable.
  - We strictly cannot use `arguments` keyword inside of it.
    ```
    const fun = () => {
      console.log(arguments);
    }
    fun(1,2,3);
    //error
    ```
