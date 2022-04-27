[Back to Content](../README.md)

# Rendering List
- to render a list we build collections of elements and include them in JSX using curly braces {}.
- eg:
    creating a collection:
    ```javascript
    const numbers = [1, 2, 3, 4, 5];
    const listItems = numbers.map((number) =>
    <li>{number}</li>
    );
    ```
    rendering it through JSX:
    ```javascript
    ReactDOM.render(
    <ul>{listItems}</ul>,
    document.getElementById('root')
    );
    ```
- but above code will give a warning that a key should be provided for list items.

# Key
- A "Key" is a special attribute you need to include when creating a list of elements.
- A key is to be unique for every element and stable(unlike index of an array) among siblings
- Keys give elements a stable identity.
- keys help react to identify which elements have been added, modified or removed which in turn result in efficient update of the UI.
- key passed in the parent component is not avialable as a prop to child component! It is reserved by react.
- why index as key not a good idea?
    - https://robinpokorny.medium.com/index-as-a-key-is-an-anti-pattern-e0349aece318
- correct key usage:
```javascript
function ListItem(props) {
  // Correct! There is no need to specify the key here:
  return <li>{props.value}</li>;
}

function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    // Correct! Key should be specified inside the array.
    <ListItem key={number.toString()} value={number} />
  );
  return (
    <ul>
      {listItems}
    </ul>
  );
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render(
  <NumberList numbers={numbers} />,
  document.getElementById('root')
);
```


[Previous](../Basic_Hooks/README.md)
<br>

[Next](../Forms/README.md)