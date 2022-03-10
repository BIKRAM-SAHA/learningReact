[Back to Content](../README.md)

# Events in React
- React events are named using camelCase, rather than lowercase.
- With JSX you pass a function as the event handler, rather than a string.
    - for example instead of:
        ```javascript
        <button onclick="activateLasers()">
            Activate Lasers
        </button>
        ```
    - in React we do:
        ```javascript
        <button onClick={activateLasers}>
            Activate Lasers
        </button>
        ```
- you cannot return false to prevent default behavior in React. You must call preventDefault explicitly.
    - that is, instead of:
        ```javascript
        <form onsubmit="console.log('You clicked submit.'); return false">
            <button type="submit">Submit</button>
        </form>
        ```
    - we do:
        ```javascript
        function Form() {
        function handleSubmit(e) {
            e.preventDefault();
            console.log('You clicked submit.');
        }

        return (
            <form onSubmit={handleSubmit}>
            <button type="submit">Submit</button>
            </form>
        );
        }
        ```
    - Here, `e` is a [synthetic event](https://reactjs.org/docs/events.html). React defines these synthetic events according to the `W3C` spec, so you don’t need to worry about cross-browser compatibility.
- You have to be careful about the meaning of this in JSX callbacks. In JavaScript, class methods are not bound by default. If you forget to bind this.handleClick and pass it to onClick, this will be undefined when the function is actually called. If you refer to a method without () after it, such as `onClick={this.handleClick}`, you should bind that method.

## Passing Arguments to Event Handlers
- it can be done using `arrow functions` and `Function.prototype.bind`
- eg:
    ```javascript
        <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
        <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
    ```
- With an arrow function, we have to pass it explicitly, but with bind any further arguments are automatically forwarded.



[Previous](../Component_Lifecycle/README.md)
<br>

[Next](../Conditional_Rendering/)