[Back to Content](../README.md)

# State
- The state is an updatable structure that is used to contain data or information by the component
- state is managed in functional components using `useState` hook
    - `useState` accepts the initial value of the state item and returns a new state variable and a function to alter its value
    - eg:
    ```javascript
    const [count, setCount]=useState(0)
    ```
- its important to note that we cannot alter the value of a state variable directly, we need to call its modifier function. Otherwise the React Component will not update its UI to reflect the changes in the data.

More about this discussed in [`useState`]() <!-- add the link to useState hook -->




[Previous](../Components/README.md)
<br>

[Next](../Props/README.md)