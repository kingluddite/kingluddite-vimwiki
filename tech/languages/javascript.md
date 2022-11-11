# JavaScript
## async ajax
* with async code we wait for data
* we need a tap on the shoulder to let us know our data is ready and that is the `.then()` that we tap onto `axios`

![example of async callback](https://i.imgur.com/u6VsUHO.png)

* Whenever we make a request with axios it returns an object called a `Promise` (a Promise is an object that gives us a little notification when some amount of work - like a network request, is completed)
  * in order to get a little tap on the shoulder when the request is completed we chain on a `.then()` method and pass it a function (usually an arrow function) and this arrow function callback will be called at some poin the in the future

```
import React from 'react';
import axios from 'axios';
import SearchBar from './SearchBar';

class App extends React.Component {
  // eslint-disable-next-line class-methods-use-this
  onSearchSubmit(term) {
    axios
      .get(`https://api.unsplash.com/search/photos`, {
        params: { query: term },
        headers: {
          Authorization:
            'Client-ID N5lZBvSduAroXytG62hsTFpsS4cCCiB3aWNpXgzZ6YU',
        },
      })
      .then((response) => {
        console.log(response);
      });
  }

  render() {
    return (
      <div className="ui container" style={{ marginTop: '10px' }}>
        <SearchBar onSubmit={this.onSearchSubmit} />
      </div>
    );
  }
}

export default App;
```

#### async await makes it cleaner
```
class App extends React.Component {
  // eslint-disable-next-line class-methods-use-this
  async onSearchSubmit(term) {
    const response = await axios.get(`https://api.unsplash.com/search/photos`, {
      params: { query: term },
      headers: {
        Authorization: 'Client-ID N5lZBvSduAroXytG62hsTFpsS4cCCiB3aWNpXgzZ6YU',
      },
    });
    console.log(response.data.results);
  }
```
##### how to use async await (much easier to read than chaining on then())
1. put async word in front of the method name
2. find what ever is returning (or whatever it taking time to resolve) and put the `await` keyword in front of that
3. whatever gets returned assign it to some variable (as we usually do)
4. Then we can freely work with that variable later on

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

## `this` rule in JavaScript
* Any time you want to find the value of `this` inside a function you don't look at the function, instead you look at where the function is called
* A cool app to get JavaScript values output
https://stephengrider.github.io/playgrounds/

* you look to the left of the `.` where the method is called

```
class Car {
  setDriveSound(sound) {
    this.sound = sound;   
  }
  
  drive() {
   return this.sound; 
  }
}

const car = new Car();
car.setDriveSound('vroom');
car.drive(); // vroom
```

* And to see this in action look at this:

```
class Car {
  setDriveSound(sound) {
    this.sound = sound;   
  }
  
  drive() {
   return this.sound; 
  }
}

const car = new Car();
car.setDriveSound('vroom');
//car.drive()

const truck = {
 sound: 'putputput',
 driveMyTruck: car.drive
}

truck.driveMyTruck() // putputput
```

## And this is undefined
* Very common problem and this is why

```
class Car {
  setDriveSound(sound) {
    this.sound = sound;   
  }
  
  drive() {
   return this.sound; 
  }
}

const car = new Car();
car.setDriveSound('vroom');


const drive = car.drive;

drive() // undefined
```

### Solution to `this` undefined
* (LEGACY SOLUTION)
* When we bind a function it will produce a new version of that function and this new functions created is fixed with the correct value of `this`  
  * and we override the broken `this` with the fixed `this` with this line

`this.drive = this.drive.bind(this)`
(see this working in below snippet of code)

```
class Car {
  constructor() {
    this.drive = this.drive.bind(this)  
  }
  
  setDriveSound(sound) {
    this.sound = sound;   
  }
  
  drive() {
   return this.sound; 
  }
}

const car = new Car();
car.setDriveSound('vroom');


const drive = car.drive;

drive(); // vroom
```

* There is a more modern way to solve this (it relies on babel which the above playground doesn't have inside it so we need to use our app code)

### This is shorthand code 
```
  onFormSubmit(event) {
    event.preventDefault();
    console.log(this);
  }
```
* for this code:

```
  onFormSubmit: function(event) {
    event.preventDefault();
    console.log(this);
  }
```

* Anytime you use the function keyword it will lead to a broken value of `this`
* And now we have arrow functions in ES6 and they have a special feature is that they automatically bind the value of `this` for all the code inside the function and this means we can avoid the legacy solution and just use an arrow function instead:

```
  onFormSubmit(event) {
    event.preventDefault();
    console.log(this); // will point to our SearchBar class component
    console.log(this.state.term); // will point to our SearchBar class component's state term value
  }
```

* Third Way
  * inline callback

```
import React, { Component } from 'react';

class SearchBar extends Component {
  // eslint-disable-next-line react/state-in-constructor
  state = { term: 'hello' };
  // eslint-disable-next-line class-methods-use-this
  // onInputChange(e) {
  //   console.log(e.target.value);
  // }

  // eslint-disable-next-line class-methods-use-this, react/no-unused-class-component-methods
  onFormSubmit(event) {
    event.preventDefault();
    // eslint-disable-next-line react/destructuring-assignment
    console.log(this);
    // eslint-disable-next-line react/destructuring-assignment
    console.log(this.state.term);
  }

  render() {
    return (
      <div className="ui segment">
        <form
          className="ui form"
          onSubmit={(event) => this.onFormSubmit(event)}
        >
          <div className="field">
            <label htmlFor="myImg">Image Search</label>
            <input
              type="text"
              // eslint-disable-next-line react/destructuring-assignment
              value={this.state.term}
              id="myImg"
              onChange={(e) =>
                this.setState({ term: e.target.value.toUpperCase() })
              }
            />
          </div>
        </form>
      </div>
    );
  }
}

export default SearchBar;
```

* We need to invoke when we have the `<form onSubmit={this.onFormSubmit(event)}` callback
  * The form will only invoke the arrow function one time - whenever we use the arrow function here - so that is why we need to include the `()` to invoke the function

## You don't need to call `super()` inside a constructor if:
* You are not extending another class

## naming props
* With normal JSX elements (example `<form>` or `<input>`) you have to have to use very specific prop names (ie `<form onSubmit={}` and `<input onChange={}` )
  * But with Custom Components (ones we author) we can name them whatever we want and so if we want to have the prop be a method that will get called on submit why not name it `onSubmit` (but remember we can name them whatever we want `makeItWorkWhenISubmitIt`)

## referencing `props` inside class based component vs functional component
* class based component `this.props.onSubmit`
* functional component `props.onSubmit`

## passing method to child class component
`parent.js`

```
import React from 'react';
import SearchBar from './SearchBar';

class App extends React.Component {
  onSearchSubmit(term) {
    console.log(this);
    console.log(term);
  }

  render() {
    return (
      <div className="ui container" style={{ marginTop: '10px' }}>
        <SearchBar onSubmit={this.onSearchSubmit} />
      </div>
    );
  }
}

export default App;
```

`child.js`

```
import React, { Component } from 'react';

class SearchBar extends Component {
  // eslint-disable-next-line react/state-in-constructor
  state = { term: '' };

  // eslint-disable-next-line class-methods-use-this, react/no-unused-class-component-methods
  onFormSubmit = (event) => {
    event.preventDefault();

    // eslint-disable-next-line react/destructuring-assignment, react/prop-types
    this.props.onSubmit(this.state.term);
  };

  render() {
    return (
      <div className="ui segment">
        <form className="ui form" onSubmit={this.onFormSubmit}>
          <div className="field">
            <label htmlFor="myImg">Image Search</label>
            <input
              type="text"
              // eslint-disable-next-line react/destructuring-assignment
              value={this.state.term}
              id="myImg"
              onChange={(e) =>
                this.setState({ term: e.target.value.toUpperCase() })
              }
            />
          </div>
        </form>
      </div>
    );
  }
}

export default SearchBar;
```

### Destrcturing arrays
```
const colors = ['red', 'green'];

colors[0];
colors[1]; // no big deal
```
* but if I want to store those array item values I need to write a lot of code
```

const colors = ['red', 'green'];

const redColor = colors[0];
const greenColor = colors[1]; // that's a lot of writing!
```

* a shortcut is to use this syntax (we are destructuring an array)
```
const colors = ['red', 'green'];
const [firstElement, secondElement] = colors 
```
* now we have 2 variables and did it in just 2 lines
* **note** in this syntax no array was created!!!

