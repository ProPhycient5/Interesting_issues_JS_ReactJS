-  **Function declaration**
```
 function square(num) {
  return num * num; 
}
```
-  **Function expression**
  When a function is stored(or assigned) to a variable.
```
const square = function(num){
  return num * num; 
}
```
- **Arrow function** — also called fat arrow function— is a new feature introduced in ES6 that is a more concise syntax for writing function expressions. 
#### There are various difference between Arrow and Regular function. We will cover cover few them.

- While both regular JavaScript functions and arrow functions work in a similar manner, there are certain differences between them.

  1. ### **Syntax**
  2. ### **<kbd>argument</kbd> keyword**
  3. ### **<kbd>this</kbd> keyword**
  4. ### **<kbd>new</kbd> keyword**    
  5. ### **Duplicate parameters**
  6. ### **Hoisting**
  7. ### **Methods**
    
  
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
 - `this` keyword cannot be used properly. That means `this` refers to the global object outside of the function context.

 -  **Regular function**
   - It may or may not be anonymous function.
   - It can be hoisted on the top of the scope because it is function declaration with contrast to function expression(in case of *arrow function*).
   - `this` and `arguments` keywords are used smoothly.
   
