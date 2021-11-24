# React

## Rules
* React wants components to start with a capital letter
  * This will differentiate it from the built in HTML characters
* Component functions must return something to be rendered
* All React components must be used directly in a component, not in some nested function

## Best Practice
* Put all components inside a `components` folder
* Put all pages inside a `pages` folder
* Name pages with capital letters just like components but the name should end with `Page`
  * Example: `AllMeetupsPage` 
* Functions names that are executed upon events end with `handler`

`example below`

```jsx
function Todo(props) {

  function handleClick() {
    console.log("clicked");
  }

  return (
    <div className="card">
      <h2>{props.text}</h2>
      <div className="actions">
        <button className="btn" type="button" onClick={handleClick}>
          Delete
        </button>
      </div>
    </div>
  );
}

export default Todo;
```

