- As long as we are copying the `primitive data types` *(i.e. Number, String, Boolean, undefined, Null)*, we really don't have to worry about whether it is 
  shallow or deep copy. Because we usually copy the value of a variable using assignment operator(`=`).
```
const a = 5;
let b = a;
console.log('a =>', a);
console.log('b =>', b);
/*
a => 5
b => 5
*/
console.log("---------After modification---------");
b = 10;
console.log('a =>', a);
console.log('b =>', b);
/*
---------After modification---------
a => 5
b => 10
*/
```

- In case of `Composite data types` - *Objects and Arrays*, copying becomes quite crucial. When you create a composite data type, the values are actually stored 
  once when instantiated, and assigning a variable just creates a reference to that value.

```
const employee = {
    name: 'Sawan',
    age: 25
};

const copyOfEmployee = employee;
console.log(employee, 'employee');
/*
{ name: 'Sawan', age: 25 } employee
*/
console.log('------------After Modification-----------');
copyOfEmployee.age = 29;
/*
Here you would expect employee object wouldn't change, but copyOfEmployee 
and employee object both share same memory address
*/
console.log(employee, 'employee');
/*
------------After Modification-----------
{ name: 'Sawan', age: 29 } employee
*/
```

- In the above example, this is what called `Shallow copy`.  This is often problematic since we expect the old variable to have original values, not the changed ones. This happens because both the old and new reference variable point to the same object in memory. So, when a new reference variable is assigned the value 
  of the old reference variable, the address stored in the old reference variable is copied into the new one. As a result if the state of the object changes 
  through any of the reference variables it is reflected for both.
  
- `Deep copy` -  Unlike the shallow copy, deep copy makes a copy of all the members of the original object, allocates separate memory location for the new object and then assigns the copied members to the new object. In this way, both the objects are independent and completely disconnected from each other and so when there is any modification to either one the other is unaffected.
  
- So same is the case for arrays.
- However, we can implement deep copy for composite data types by the following ways:
1.  `map()`, `forEach()` and `slice()` methods ---> [applicable for arrays]
2. `Object.assign()` and `Object.create()` methods ---> [applicable for objects]
3.  Spread operator (`...`) ---> [applicable for both]
4. `JSON.stringify()` and `JSON.parse()` methods ---> [applicable for both]
5. Using `structuredClone()` JS built-in method ---> [applicable for both]
6. Using **Lodash** JS library ---> [applicable for both]
7. Creating own custom functions ---> [applicable for both]

- Considering 1, 2 and 3 those ways only does not perform deep clone technically (not for nested objects or multi-dimensional arrays). 
- Whereas 4th one does deep clone for even nested objects but there are various flaws to perform perfect deep clone.
  - Unable handle **Recursive data structure** (usually linked list and tree)
  - `JSON.stringify()` fails if the value contains other JS built-ins (like `Map`, `Set`, `Date`, `RegExp` or `ArrayBuffer`)
  - `JSON.stringify()` discards functions.
  - *In short, this approach fails to handle non-serializable data.*

- 5th one is a JS standard method which has addresses various (not all) shortcomings of the `JSON.stringify()` approach. 
  But it still has various shortcomings:
  - If you use `structuredClone()` with a class instance, you’ll get a plain object as the return value, as structured cloning discards the object’s prototype chain.
  - Unable to handle Functions.
  - Some values are not structured cloneable, most notably Error and DOM nodes.
 
- Coming to 6th,  `cloneDeep()` method of Lodash library helps in deep cloning of an object and also clones the [non-serializable properties](https://www.oreilly.com/library/view/javascript-the-definitive/9781449393854/ch06s09.html) which were a limitation in the JSON.stringify() approach. By far, it is the best and commonly used method. As all knows, one creates a custom function with reference to the particular object.

- **Serializable data(or properties)** are those data that undergoes `Serialization` where an object(or data structure) is translated into a format suitable for transfer over a network, or storage (e.g. in an array buffer or file format) using `JSON.stringify()` method.
   - Objects, arrays, strings, finite numbers, true, false, and null can be serialized 
   - NaN, Infinity & -Infinity(all these serialized to null) and Date objects are serialized to ISO-formatted date strings, but `JSON.parse()` leaves these in string form and does not restore the original Date object.
   - Function, RegExp, and Error objects and the undefined value cannot be serialized or restored. 


Credits:
1. [GeekForGeek source](https://www.geeksforgeeks.org/what-is-shallow-copy-and-deep-copy-in-javascript/)
2. [MDN docs -1](https://developer.mozilla.org/en-US/docs/Glossary/Deep_copy)
3. [MDN docs -1](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy)
4. [Siddharth Sunchu medium blog](https://javascript.plainenglish.io/copies-of-javascript-shallow-and-deep-copy-ac7f8dcd1dd0)
5. [Good article on structureClone method](https://web.dev/structured-clone/)
