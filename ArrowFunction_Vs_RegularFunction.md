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
        - 
        ```
        // ES5---> Regular function
         var add = function(x, y) {
           return x + y
         };

       // ES6---> Arrow function
         let add = (x, y) =>  x + y
        ```
       - In regular function, it's mandatory to use <kbd>return</kbd> to return any value. If you don’t return anything then the function will return undefined.
       - 
       ```
        function regFunc() {
             return "Regular Function";
        }
        
        regFunc(); 

        // Regular Function
        function regFunc() {
            console.log("Regular Function")
        }regFunc(); 
       // Regular Function
       // undefined
       ```
       - If the arrow function contains one expression, the use of <kbd>return</kbd> is optional else it is required to return in order to return the output                  generated by the multiple line of code.
       - Moreover, the use of <kbd>{ }</kbd> and  <kbd>( )</kbd> is optional for the function carrying one line of statement and one parameter respectively.
         ```
         //No need of curly and simple bracket because below code consists of one parameter and one statement.
         let add = x => x + x;
         ``` 
       - If there is no parameter, we can write in the following manner.
         ```
         let arrowFunc = _ => console.log("Arrow Function");
         ```
        
        
        
        
        
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
   
