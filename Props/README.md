[Back to Content](../README.md)

# Props
- standing for properties these are attributes passed from the parent component and and are recieved by the children component similar to arguments of a js function
- are immutable, hence cannot be modified from inside the component

## Default props
- It is not necessary to always pass down a prop to child component. You can set default props
- for class based components we can do that by setting to directly to the component constructor. eg:
    ```javascript
    import React, { Component } from 'react';  
    class App extends React.Component {  
    render() {     
        return (  
            <div>  
                <h1>Default Props Example</h1>  
                <h3>Welcome to {this.props.name}</h3>   
            </div>  
            );  
        }  
    }  
    App.defaultProps = {  
    name: "Hello program"  
    }  
    export default App;  
    ```
- function based components

## Props validation
- PropTypes exports a range of validators that can be used to make sure the data you receive is valid, forcing the correct usage of props and avoiding future bugs
- for performance reasons, `propTypes` is only checked in development mode.
- for props validation, you must import PropTypes using: `import PropTypes from 'prop-types'`
- Syntax:
    ```javascript
    import PropTypes from 'prop-types'

    function HelloWorldComponent({ name }) {
    return (
        <div>Hello, {name}</div>
    )
    }

    HelloWorldComponent.propTypes = { 
    name: PropTypes.string
    //and other similar validators for other props
    }

    export default HelloWorldComponent
    ```
- different provided validators:
    ```javascript
    import PropTypes from 'prop-types';

    MyComponent.propTypes = {
    // You can declare that a prop is a specific JS type. By default, these
    // are all optional.
    optionalArray: PropTypes.array,
    optionalBool: PropTypes.bool,
    optionalFunc: PropTypes.func,
    optionalNumber: PropTypes.number,
    optionalObject: PropTypes.object,
    optionalString: PropTypes.string,
    optionalSymbol: PropTypes.symbol,

    // Anything that can be rendered: numbers, strings, elements or an array
    // (or fragment) containing these types.
    optionalNode: PropTypes.node,

    // A React element.
    optionalElement: PropTypes.element,

    //only a single child can be passed to a component as children.
    children: PropTypes.element.isRequired,

    // A React element type (ie. MyComponent).
    optionalElementType: PropTypes.elementType,

    // You can also declare that a prop is an instance of a class. This uses
    // JS's instanceof operator.
    optionalMessage: PropTypes.instanceOf(Message),

    // You can ensure that your prop is limited to specific values by treating
    // it as an enum.
    optionalEnum: PropTypes.oneOf(['News', 'Photos']),

    // An object that could be one of many types
    optionalUnion: PropTypes.oneOfType([
        PropTypes.string,
        PropTypes.number,
        PropTypes.instanceOf(Message)
    ]),

    // An array of a certain type
    optionalArrayOf: PropTypes.arrayOf(PropTypes.number),

    // An object with property values of a certain type
    optionalObjectOf: PropTypes.objectOf(PropTypes.number),

    // An object taking on a particular shape
    optionalObjectWithShape: PropTypes.shape({
        color: PropTypes.string,
        fontSize: PropTypes.number
    }),

    // An object with warnings on extra properties
    optionalObjectWithStrictShape: PropTypes.exact({
        name: PropTypes.string,
        quantity: PropTypes.number
    }),   

    // You can chain any of the above with `isRequired` to make sure a warning
    // is shown if the prop isn't provided.
    requiredFunc: PropTypes.func.isRequired,

    // A required value of any data type
    requiredAny: PropTypes.any.isRequired,

    // You can also specify a custom validator. It should return an Error
    // object if the validation fails. Don't `console.warn` or throw, as this
    // won't work inside `oneOfType`.
    customProp: function(props, propName, componentName) {
        if (!/matchme/.test(props[propName])) {
        return new Error(
            'Invalid prop `' + propName + '` supplied to' +
            ' `' + componentName + '`. Validation failed.'
        );
        }
    },

    // You can also supply a custom validator to `arrayOf` and `objectOf`.
    // It should return an Error object if the validation fails. The validator
    // will be called for each key in the array or object. The first two
    // arguments of the validator are the array or object itself, and the
    // current item's key.
    customArrayProp: PropTypes.arrayOf(function(propValue, key, componentName, location, propFullName) {
        if (!/matchme/.test(propValue[key])) {
        return new Error(
            'Invalid prop `' + propFullName + '` supplied to' +
            ' `' + componentName + '`. Validation failed.'
        );
        }
    })
    };
    ```

## Props VS State
| SN | Props	| State| 
|---|---|---| 
| 1. | Props are read-only.	| State changes can be asynchronous.| 
| 2. | Props are immutable.	| State is mutable.| 
| 3. | Props allow you to pass data from one component to other components as an argument.	| State holds information about the components.| 
| 4. | Props can be accessed by the child component. | State cannot be accessed by child components.| 
| 5. | Props are used to communicate between components. | States can be used for rendering dynamic changes with the component.| 
| 6. | Stateless component can have Props. | Stateless components cannot have State.| 
| 7. | Props make components reusable. | State cannot make components reusable.| 
| 8. | Props are external and controlled by whatever renders the component. | The State is internal and controlled by the React Component itself.| 

### Note:
- There is a special prop called `children`, that contains the value of anything passed between opening and closing tags of a component. eg:
    ```javascript
    <WelcomeMessage>Here we go!</WelcomeMessage>
    ```

    in this case we can access the `Here we go!` using children prop:
    ```javascript
    function WelcomeMessage({children}){
        return  <p>{children}</p>
    }
    ```


[Previous](../State/README.md)
<br>

[Next](../Component_Lifecycle/README.md)