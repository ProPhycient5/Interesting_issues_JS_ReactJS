## Basic points regarding `useReducer`
1. It is a hook that is used for state management.
2. It is an alternative to `useState`.
3. `useState` is built using `useReducer`.
4. `useReducer` is a primitive react hook.

## Similarities between `reduce` method and `useReducer` hook.
| `reduce()` in JavaScript | `useReducer` hook in React |
| -------------------------|----------------------------|
| array.reduce(reducerFn, initialValue) | useReducer(reducerFn, initialState) |
| singleValue = reduce(accumulator, itemValue) | newState = reducer(currentStatem, action) |
| `reduce` method return a single value | `useReducer` return a pair of values `[newState, dispatch]` |

##### Action is the instruction of the reducer function.

##### The [following link](https://codesandbox.io/s/usereducer-hook-w9qqtg) is the demonstration of implementation of simple `useReducer` hook.
