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

- In case of `Composite data` types - Objects and Arrays, copying becomes quite crucial. When you create a composite data type, the values are actually stored 
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

- In the above example, this is what called `Shallow` copy.  This is often problematic since we expect the old variable to have original values, not the changed ones.
  This happens because both the old and new reference variable point to the same object in memory. So, when a new reference variable is assigned the value 
  of the old reference variable, the address stored in the old reference variable is copied into the new one. As a result if the state of the object changes 
  through any of the reference variables it is reflected for both.
  
  
  
  
  
  
  
  
  
  
