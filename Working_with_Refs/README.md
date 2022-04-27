[Back to Content](../README.md)

# Refs
Refs provide a way to access DOM nodes or React elements created in the render method.


# useRef
useRef returns a mutable ref object whose .current property is initialized to the passed argument (initialValue). The returned object will persist for the full lifetime of the component.
```jsx
const refContainer = useRef(initialValue);
```
- a way to access the DOM: If you pass a ref object to React with `<div ref={myRef} />`, React will set its .current property to the corresponding DOM node whenever that node changes.
    ```jsx
    function TextInputWithFocusButton() {
    const inputEl = useRef(null);
    const onButtonClick = () => {
        // `current` points to the mounted text input element
        inputEl.current.focus();
    };
    return (
        <>
        <input ref={inputEl} type="text" />
        <button onClick={onButtonClick}>Focus the input</button>
        </>
    );
    }
    ```
- using like state variable but without update on changes: useRef’s Ref object is handy for keeping any mutable value around similar to how you’d use instance fields in classes. This works because useRef() creates a plain JavaScript object. The only difference between useRef() and creating a {current: ...} object yourself is that useRef will give you the same ref object on every render.



[Previous](../Forms/README.md)
<br>

[Next]()