[Back to Content](../README.md)

# Hooks
Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes.

## Rules of Hooks
- Don’t call Hooks inside loops, conditions, or nested functions. Instead, always use Hooks at the top level of your React function, before any early returns. By following this rule, you ensure that Hooks are called in the same order each time a component renders. [Reason](https://reactjs.org/docs/hooks-rules.html#explanation)
- Don’t call Hooks from regular JavaScript functions. Instead, you can:
    - Call Hooks from React function components.
    - Call Hooks from custom Hooks

# Basic Hooks
## useState:
- what it does:
    - It declares a “state variable”.
    - This is a way to “preserve” some values between the function calls
    - Normally, variables “disappear” when the function exits but state variables are preserved by React.
- arguments:
    - The only argument to the useState() Hook is the initial state. 
    - the initial state is used only on first render, later on subsequent renders useState() returns the current state.
- returns:
    - returns a pair of values: the current state and a function that updates it.
- eg:
    ```jsx
    import React, { useState } from 'react';

    function Example() {
    // Declare a new state variable, which we'll call "count"
    const [count, setCount] = useState(0);
    ```
- reading the state:
    - we can use `count` directly
    - ```jsx
        <p>You clicked {count} times</p>
        ```
- Updating state:
    - we use the `setCount` function returned by `useState()`
    - ```jsx
        <button onClick={() => setCount(count + 1)}>
        Click me
        </button>
        ```
## useEffect:
- lets you perform side-effects
- Usage:
    - No dependency passed:
        ```javascript
        useEffect(() => {
        //Runs on every render
        });
        ```
    - An empty array as dependency: signifies effect not dependent on anything
        ```javascript
        useEffect(() => {
        //Runs only on the first render
        }, []);
        ```
    - Props or State as dependency: signifies effect dependent on specified values in array
        ```javascript
        useEffect(() => {
        //Runs on the first render
        //And any time any dependency value changes
        }, [prop, state]);
        ```
    - returning clean-up function: run clean-up function
        ```javascript
            useEffect(() => {
            //Runs on every re-render
            return function somefunction(){
                //Runs as clean-up to every re-rendered
            }
            });
        ```
        ```javascript
        useEffect(() => {
        //Runs on the first render
        return function somefunction(){
            //Runs on unMounting
        }
        },[]);
        ```
        ```javascript
        useEffect(() => {
        //Runs on change in dependency
        return function somefunction(){
            //Runs on re-renders on change in dependency
        }
        },[dependecies]);
        ```
## useContext:
-  Context provides a way to pass data through the component tree without having to pass props down manually at every level
- creating a context object
    ```jsx
    const ThemeContext = React.createContext(themes.light);
    ```
- wraping the context.Provider: the current context value is determined by the nearest `<MyContext.Provider>`
    ```jsx
    function App() {
    return (
        <ThemeContext.Provider value={themes.dark}>
        <Toolbar />
        </ThemeContext.Provider>
    );
    ```
- using the context
    ```jsx
    function ThemedButton() {
    const theme = useContext(ThemeContext);
    return (
        <button style={{ background: theme.background, color: theme.foreground }}>
        I am styled by theme context!
        </button>
    );
    }
    ```
    - A component calling useContext will always re-render when the context value changes
    - useContext(MyContext) only lets you read the context and subscribe to its changes. You still need a `<MyContext.Provider>` above in the tree to provide the value for this context.



[Previous](../Conditional_Rendering/README.md)
<br>

[Next](../List_and_keys/README.md)