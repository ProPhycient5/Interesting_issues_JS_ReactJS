`async await`.

### async function always return a promise, even if we return string, boolean, number or any data type. It will be wrapped within a promise.

Ex:
```
async function getData(){
 return "Namaste";
}
```

const dataPromise = getData();
dataPromise.then((res) => console.log(res));

### async-await is used to handle promises.cawait can only be used inside an async function

```
const p = new Promise((resolve, reject) => {
  setTimeout(() => {
   resolve("Promise Resolved Value!!!");
}, 10000)
});
```
### JS Engine appears to be waiting for promise to be fulfilled. Actually the async func gets suspended poped out of callstack until it is resolved or rejected. Then JS excution works later that line.
```
async function handlePromise(){

 const val = await p;
 console.log("Nameste JavaScript");
 console.log(val); 
}

handlePromise();
```

### `async` is the keyword used before function and `await` is used inside the async func to handle the promises.
