[Back to Content](../README.md)

# JSX
- JSX(JavaScript Extension) is an HTML-like syntax used by React that extends ECMAScript so that HTML-like syntax can co-exist with JavaScript/React code, which is further transformed by preprocessors (i.e., transpilers like babel) to standard JS objects that a JavaScript engine will parse.
- JSX provides you to write HTML/XML-like structures (e.g., DOM-like tree structures) in the same file where you write JavaScript code
- Just like XML/HTML, JSX tags have a tag name, attributes, and children.
- eg:
    ```JSX
    <div>Hello JavaTpoint</div>  
    ```
    is converted to
    ```javascript
    React.createElement("div", null, "Hello JavaTpoint");  
    ```
    The above line creates a react element using passed three arguments:
    1. first is the name of the element which is div
    2. second is the attributes passed in the div tag 
    3. last is the content you pass

## Why JSX?
- Faster: Optimizations are done while translating code to JavaScript so is faster than regular javascript
- Instead of separating technologies by putting the markup and logic in different files, React uses components that contain both
- Type-safe: most of the errors can be found at compilation time
- makes it easier to create templates and build UI interfaces

## JSX Attributes
- use camelCase
- for custom attributes the prefix "data-" is used
- few common keywords of JS and HTML are named differently like class(HTML) becomes className(JSX) and for(HTML) becomes HTMLFor(JSX)


### Note:
- comments
    ```Javascript
    {/* This is a comment in JSX */}   
    ```
- We can embed JavaScript statement in JSX between `{ }` but just one statement for every curly bracket block and the statement must return something.
- NOTE: JSX cannot allow to use if-else statements. Instead of it, you can use conditional (ternary) expressions.
    ```javascript
    import React, { Component } from 'react';  
    class App extends Component{  
    render(){  
        var i = 5;  
        return (  
            <div>  
                <h1>{i == 1 ? 'True!' : 'False!'}</h1>  
            </div>  
        );  
    }  
    }  
    export default App; 
    ```

[Previous](../Create_React_App/README.md)
<br>

[Next](../Components/README.md)