[Back to Content](../README.md)

# Forms in React
- There can be two ways of implementing forms in react:
    - using Controlled Components
        - Controlled components are created using two simple steps:
            - have the current value of the `input` fields from a state variable using `useState` hook
            - changing the state value by handling the `onChange` event on the `input fields`
        - eg:
        ```javascript
        import React, { useState } from "react";


        function TestComponent() {
        const [nameState, setNameState] = useState('')
        const [age, setAge] = useState(0)

        const handleNameChange = (e) =>{
            setNameState(e.target.value)
        }
        const handleAgeChange = (e) =>{
            setAge(e.target.value)
        }
        const handleSubmit = (e) =>{
            e.preventDefault()
            alert(nameState+" "+age)
            setNameState('')
            setAge('')
        }
        
        return (
            <form onSubmit={handleSubmit}>
            <div>
            <label name='Name'>Enter Name</label>
            <input type='text' name="Name" onChange={handleNameChange} value={nameState}></input>
            </div>
            <div>
            <label name='Age'>Enter Age</label>
            <input type="number" name="Age" onChange={handleAgeChange} value={age}/>
            </div>
            <button type="submit">Submit</button>
            </form>
        );
        }
        ```
    - using Uncontrolled Components
        - To write an uncontrolled component, instead of writing an event handler for every state update, you can use a ref to get form values from the DOM.
        - uncontrolled component keeps the source of truth in the DOM hence is sometimes easier to integrate React and non-React code when using uncontrolled components.
        - A quick and dirty approach with slightly less code
        - eg:
        ```javascript
        import React, { useRef } from "react";
        import "./styles.css";

        export default function App() {
        const inputRef = useRef();

        function updateValue() {
            inputRef.current.value = "Anshul";
        }

        function getValue() {
            alert(inputRef.current.value);
        }

        return (
            <div className="App">
            <h1>Hello CodeSandbox</h1>
            <h2>Start editing to see some magic happen!</h2>
            Uncontrolled Element: <input type="text" ref={inputRef} />
            <input type="button" onClick={updateValue} value="Click to Update" />
            <input type="button" onClick={getValue} value="Click to Get Values" />
            </div>
        );
        }
        ```

## Controlled VS Uncontrolled components
![alt](./controlled%20vs%20uncontrolled.png)

NOTE:
- In React, an `<input type="file" />` is always an uncontrolled component because its value can only be set by a user. Use the File API to interact with the files and ref to the DOM node to access file(s) in a submit handler.
- In the React rendering lifecycle, the value attribute on form elements will override the value in the DOM. With an uncontrolled component, you often want React to specify the initial value, but leave subsequent updates uncontrolled. To handle this you can specify a defaultValue attribute instead of value.
    - eg:
    ```javascript
    return (
        <form onSubmit={this.handleSubmit}>
        <label>
            Name:
            <input
            defaultValue="Bob"
            type="text"
            ref={this.input} />
        </label>
        <input type="submit" value="Submit" />
        </form>
    );
    ```
- [Formik](https://formik.org/) is one of the popular choices with complete solution including validation, keeping track of the visited fields, and handling form submission. 

[Previous](../List_and_keys/README.md)
<br>

[Next](../Working_with_Refs/README.md)