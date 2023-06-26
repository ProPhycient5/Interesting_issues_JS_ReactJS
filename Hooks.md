1. Hooks are the functions to use some react features in functional component.
2. In other words, Hooks are the functions that enable functional component work like Class component.

## `useState`:
  1. `useState` hook enable functional component to add state in Functional Component.
  2. State is nothing but just values or variables of your component.

## `useEffect`:
   1. `useEffect` is used to perform side effects in our component.
   2. Side Effects are actions which are performed with the 'Outside world'.
   3. Some common side effects are:
      1. Fetching data from API.
      2. updating the DOM document & windown
      3. Time functions setTimeout & setInterval
   4. useEffect without dependency array, runs in any change of that concerned component.
   5. In useEffect, where clean-up function is mentioned, that runs first, then callback function runs later.

## `useContext` 
   In useContext hook, three steps are required:
  1. Creating the context. (using createContext() ex: `const User = createContext()` in top component)
  2. Providing the context. (using `<User.Provider value={'John'}>`)
  3. Consuming the context. (using `useContext()` in the desired child component)

 ## `useRef`
  1. It allows us to access DOM elements.
  2. It holds a mutable value between re-render.

This is the link of [codesandbox](https://codesandbox.io/s/react-hooks-d5vy2w?file=/src/App.js) where all of the above hooks are experimented as per theory.

## `useReducer` 
   1. useReducer hook is used to manage state in our react application.
   2. It works like a state management tool.
This is the link of [codesandbox](https://codesandbox.io/s/usereducer-hooks-v8xqn6?file=/src/App.js) where `useReducer` is experimented.

## `useLayoutEffect`
   1. the syntax is the same as in `useEffect`.
   2. useLayoutEffect runs before the DOM is painted on the browser which is reversed in the case of useEffect.
   3. It runs synchronously.
   4. The most common use case of useLayoutEffect is to get the dimension of the layout, that's why its name is useLayoutEffect. 
This is the link of [codesandbox](https://codesandbox.io/s/uselayouteffect-fd3jgh?file=/src/App.js) where `useLayoutEffect` is experimented.

 
