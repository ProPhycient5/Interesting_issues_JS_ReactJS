Follow the given [code base](https://codesandbox.io/s/usecallback-hook-3g3d5n) for following explaination, (consider removing `React.memo` and `useCallback`) 

#### 1. In initial render, all 5 child components get rerendered which can be validated from console logs.

#### 2. Later when we click either of the buttons, all 5 child components of the parent component rerendered.

#### 3. So, in order to optimize, we use `React.memo` that is HOC that will prevent the components to re-render if its props hasn't changed. 

#### 4. `React.memo` has nothing to do with hooks.

#### 5. By binding with `React.memo`, we optimize the App. However, we find that when we click on `Increment age` btn, the following console logs are executed:
```
rendered  Age
rendered  Increment Age
rendered  Increment Salary
```
#### 6. From the above logs, it is evident that props of `Increment Salary` has changed, although we haven't handle it directly.

#### 7. As parent component gets re-rendered, the `handleSalary` is executed again that's why it's a new prop to the 
` <Button handleClick={handleSalary}>Increment Salary</Button>` components. 

#### 8. `useCallback` is a hook that will return a memoized version of the callback function that only changes if one the dependendies has changed.
#### 9. It is useful when passing callbacks to optimized child components that rely on reference equality  to prevent unnecessary renders.

#### 10. React Component Comparison: In React, reference equality is crucial for optimizing re-renders. When props or state change and they are objects or arrays,
React uses reference equality to decide whether to re-render a component.
