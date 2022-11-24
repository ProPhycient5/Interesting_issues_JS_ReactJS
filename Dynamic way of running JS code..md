### If there is use case, where we want to execute JS code dynamically which is store as string. we execute in two ways
1. #### Using `Function` constructor:
```
const jsCode = `console.log("executed");`
const func_wrapper = new Function(value);
func_wrapper();
```
But this method has some security concern to application. [Read more](https://snyk.io/blog/5-ways-to-prevent-code-injection-in-javascript-and-node-js/).

2. #### Create script tag:

```
const jsCode = `console.log("executed")
let script = document.createElement("script");
script.type = "application/javascript";
script.text = jsCode;
document.body.appendChild(script);
```
This is the better and secured method to execute JS code dynamically which is stored as a string.
