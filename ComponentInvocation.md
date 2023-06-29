# In this section, we get to learn about the best practice for invoking a component and the reasons behind it.



1. In the following code, the EmailComponent is invoked as a regular function instead of being used as a JSX component. To correct this, we need to use 
   angle brackets (<EmailComponent />) to render the EmailComponent as a JSX component. But why? 🤔

2. When we invoke the component as a regular function, we merged App and EmailComponent into a single supercomponent and turned the email field into a custom hook.

3. However, this approach causes unnecessary re-rendering of the App component whenever the EmailComponent updates. This violates the encapsulation of re-render 
   principle (one reason 🟢).

4. In ReactJS, the encapsulation of re-render refers to the behavior where the rendering of components is optimized to only update the necessary parts of the user interface.
   This means that when a component's state or props change, React will intelligently determine which parts of the UI need to be updated and only update those 
   specific parts, rather than re-rendering the entire component.

5. The app crashes because when the App is initially loaded, there is one hook. However, when the user checks the checkbox, the App has two hooks in the condition 
   while rendering, which throws an error as Rendered more hooks than during the previous render (2nd reason 🟢).

6. Moreover, when the EmailComponent is invoked as a regular function, React doesn't recognize it as a component instance and cannot manage its lifecycle or state properly. 
   This leads to unexpected behavior and issues when working with component states, hooks, and lifecycle methods.

7. We can fix this issue by using JSX syntax <EmailComponent /> ✌🏽.

```
import "./styles.css";
import { useState } from "react";

const EmailComponent = () => {
  const [email, setEmail] = useState("");

  return (
    <input
      type="email"
      value={email}
      onChange={(e) => setEmail(e.target.value)}
    />
  );
};

export default function App() {
  const [showEmail, setShowEmail] = useState(false);

  return (
    <div className="App">
      <h2>Invoking Component Function Directly</h2>
      <div>
        <input
          type="checkbox"
          checked={showEmail}
          onChange={(e) => setShowEmail(e.target.checked)}
        />
        <label htmlFor="showEmail">Show Email</label>
      </div>
      {showEmail && EmailComponent()} {/* Incorrect component invocation */}
      {/* {showEmail && <EmailComponent />} */}   /// Correct component invocation
    </div>
  );
}
```
You can try the revised code in this [sandbox](https://codesandbox.io/s/invokingcomponentfunctiondirectly-36jdd9?file=/src/App.js).

