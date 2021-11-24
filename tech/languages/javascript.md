# JavaScript
## Useful functions
* Generate a random string id

```js
const randomId = () => {
  // generate a random number, convert it to a string,
  // toString(36) // base 36 (the string will be filled with numbers and letters, all numbers from 0-9, all letters from a-z)
  // we just take a portion of the string we get back 
  return Math.random().toString(36).substr(2, 5);
}
```
