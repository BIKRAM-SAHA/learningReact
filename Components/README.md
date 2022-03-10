[Back to Content](../README.md)

# Components
- core building block of any React application which are reuseable
- makes the task of building UI easier
- Each component exists in the same space but work independently and finally merge at their parent component hence forming the final UI
- every Component has its own structure, methods and APIs
- Note: Always start component names with a capital letter. React treats components starting with lowercase letters as DOM tags.

## Types of Components
<details>

<summary>Functional Components</summary>

- Also known as stateless components, these components are like simple javascript functions that may or may not receive arguments as props and return what should be rendered in the UI.
- to use state in these components you have to use the `useState` hook
- example:
    ```javascript
    function WelcomeMessage(props) {  
    return <h1>Welcome to the , {props.name}</h1>;  
    }  
    ```
</details>

<details>

<summary>Class Components</summary>

- requires you to extend from React.Component and create a render function which returns a React element
- eg:
    ```javascript
    class MyComponent extends React.Component {  
    render() {  
        return (  
        <div>This is main component.</div>  
        );  
    }  
    }  
    ```
</details>

[Previous](../JSX/README.md)
<br>

[Next](../State/README.md)