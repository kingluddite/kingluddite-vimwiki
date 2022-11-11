# Modern React with Redux
* Master React and Redux with React Router, Webpack, and Create-React-App. Includes Hooks!
* Created by Stephen Grider (last updated 9/22)
 
## Apps Practice Location
[dev practice udemy modern react with redux grider](dev/practice/udemy/modern-react-with-redux-grider)
### Tips
* I will mention, just as an FYI, that wrapping your root App in StrictMode will cause extra renders
* tradtionally we put imports for 3rd party packages or dependencies that are installed into our projects first, above files that you create (local to your app - not a technical reason for this but it is a convention)
* two ways to make AJAX calls to API in React (both used for managing network requests fetching some amount of data)
  * axios (3rd party package library - install with npm)
  * fetch (function built into modern browsers)
* fetch vs axios
  * fetch is built in so no npm install needed and smaller file size but a con is fetch is a far more basic and lower level function to use to fetch data - it's not bad but if you use fetch you will need to write a lot of code that is already written for you in axios
  * recommendation - use axios for all your projects personal and professional because axios handles requests in a very predictable fashion
  * fetch has corner cases that are not great to work with
* React developers want to work with `controlled` vs `uncontrolled` components
* using `setState()` is additive
* Put functional component at bottom of file and config objects and helper functions at the top (best practice)
* Anytime we make a component we ALWAYS try to not have multiple return statements inside a render method - saves you time and is flexible solutio
* If you have a class name component named something like `SeasonDisplay`, if you are styling that component in the root element of that JSX element container use a matching className like `season-display`
* benefit - this makes it a lot easier to apply CSS in the future because you will always know your SeasonDisplay component will always have a className of `season-displa`
* We default to and empty array or empty object instead of `null` or an empty string - that allows us to call certain functions on the state property without worrying about finding 'function not found' or something like that error
  * if you assigned `state = { images: null }` when initializing your state in a react class component and later on inside of the class you called `this.state.images.map()` - the map() function is built into the array object in JavaScript - so if I tried to call `map()` on a value of `null` I would end up with an error message but if I called `map()` on an empty array `[]` I'm not going to get an error
## Hooks
* when you re-render state in a functional compnonent the default value is no longer used, it is only used upon the first render of that component - so when you call your setter useState function it will replace the default state value used in useState

#### Naming Conventions
* name your event handlers `onInputChange` or `onInputClick` - it reads nice for you and your team (this is Community convention on how we name our handlers)
  * `on` + `name of element we are assigning this callback to` + `name of event we are listening/watching for` (slightly more popular than using `handle` and my preference)
  * (variable is to name all with `handle` like `handleInputChange`)
  * **note** we can name our event handlers anything we want but the propname is required so `onClick` or `onSubmit` or `onChange` must be spelled exactly or events won't fire

```
const SeasonDisplay = (props) => {
  const season = getSeason(props.lat, new Date().getMonth());
  const { seasonText, iconName } = seasonConfig[season];

  return (
    <div className={`season-display ${season}`}>
      <i className={`icon-left massive ${iconName} icon`} />
      <h1>{seasonText}</h1>
      <i className={`icon-right massive ${iconName} icon`} />
    </div>
  );
};

export default SeasonDisplay;
```

### defaultProps
* If you accept props but don't send props this allows you to set in one elegant location a default value
 
```
const LoadingSpinner = (props) => (
  <div className="ui active dimmer">
    <div className="ui big text loader">{props.message}</div>
  </div>
);

LoadingSpinner.defaultProps = {
  message: 'Loading...',
};
```

### Notes
* **IMPORTANT CONCEPT** When you import a CSS file what is happening?
  * You might think that if we import a CSS file into a JavaScript file we just take the CSS and paste it directly into the JavaScript file - that is not what is happening - what is happening is webpack (bundler and open source dependency inside our project right now - it comes baked into the CRA app we created) takes all these different files and joins them together, it will see we are importing a CSS file, it will take the contents out of there and then stick it into the index.html file
* render() gets called a ton of times
* The browser doesn't understand JSX
* So we need to take JSX and transpile it into valid JavaScript that we can safely run inside the browser
* We have something running inside our terminal that is doing all this for us and we call that our Development Server (aka Dev Server)
  * The Dev Server will use tools internally to take all our files CRA gave us (index.js, App.js, reportWebVitals.js) and take the JSX inside them and convert them into normal JavaScript - The tool that does that is called `Babel`
  * `Webpack` is another tool our Dev Server is using and it takes all our files and mashes them together into one file called `bundle.js`

## Big Picture 
![big picture screenshot](https://i.imgur.com/i9IlSuB.png)

1. The Browser at localhost:3000 sends a HTTP Request to the React Dev Server
2. The React Dev Server sends index.html back as a response
3. Inside the index.html there is a script tag pointing to bundle.js (the mash of all our files with JSX) and makes a HTTP request again to the Dev Server for bundle.js
4. The Dev Server sends bundle.js as a Response back to the browser

## Do we need all these files to run our react app that CRA created for us?
No

Here are the files we need:

* index.js (first file that gets executed when our app runs)  
* index.tml (skeleton for the react app)
* package.json (lists depenencies)
* package-lock.json (lists depenencies)
* node_modules (contains dependencies our app needs)
 
![This shows you a list of all the files and what they are for](
https://i.imgur.com/rvzBALb.png)

## Why do we need to import both React and ReactDOM libraries?
* `React` is a Library that defines what a component is and how multiple components work together
* `ReactDOM` is a library that knows how to get a component to show up in the browser
* ReactNative is a Library that knows how to get a component to show up in your mobile phone

## babel repl
https://babeljs.io/repl

type jsx on left and it will output JavaScript on right

### try it out
type: `<h1>hello world</h1>` and watch how createElement() does it's magic

why use jsx at all? When our structure gets complicated it's a heck of a lot of typing and jsx makes our lives so much easier but allowing us to declare what we want in simple code and babel does all the heavy lifting

* Here is a more complicated structure

```
<div>
 <h1>hello world</h1>
 <ul>
  <li>red</li> 
  <li>green</li> 
  <li>blue</li> 
 </ul>
</div>
```

## IMPORTANT jsx must return a component
* If we don't React won't use it
* `<h1>hello world</h1>` will never show up in the browser and is just an instruction for React to make an element - we have to `return` it from a component for React to use it
  * Similar to the DOM that creates an element in the ether and we never see it until we attach it to an element in the browser    

## dynamic jsx
* random render dynamic text
```js
function App() {
  let message = 'Bye there'
  if (Math.random() > 0.5) {
    message = 'Hello there!'
  }
  return <h1>{message}</h1>
}
```

## React does not render
* boolean
* null
* undefined

### other edge case - if you try to print out
* Will just output 123 (not what you probably want)
```js
function App() {
  let message = [1,2,3]
  if (Math.random() > 0.5) {
    message = 'Hello there!'
  }
  return <h1>{message}</h1>
}
```

## You can't print out objects
* You will get a console error that says "Objects are not valid as a React child"
* **warning** If you ever try to show an object in JSX you will get an error

```js
function App() {
  let message = {}
  if (Math.random() > 0.5) {
    message = 'Hello there!'
  }
  return <h1>{message}</h1>
}
```

## REMEMBER - We will most likely use numbers or strings in JSX

## Gotcha - Common Error: React cannot show an object as text content
* THIS IS BAD
* VERY COMMON ERROR

```js
function App() {
  const config = { color: 'red' };
  
  return (
    <div>
        {config}
    </div>
  )
}
```

![component layout pattern](https://i.imgur.com/eV9UcU8.png)

## props as arrays objects and variables
![how to define props of arrays objects variables](https://i.imgur.com/aQ6M4Iu.png)
* We can't render objects to screen in React
* But we can provide objects and arrays as a prop value

## 5 rules converting HTML to JSX
1. All prop names follow camelCase (react errors will tip you off if you violate this rule)
2. Number attributes use curly braces (if html uses `""` around number JSX uses `{}`)
3. Boolean 'true' can be written with just a property name but 'False' should be written with curly braces
   * `<input spellCheck />` or `<input spellCheck={false}` 
4. The `class` attribute is written as `className`
5. In-line styles are provided as objects
  * `<input style={{ paddingTop: "10px", paddingLeft: "20px"}} />`

## Screenshots 
* ![what is cra](https://i.imgur.com/6rMCksC.png)
* [cra diagram requests](https://i.imgur.com/UlvKqIC.png)
* [files and cra dev server](https://i.imgur.com/AbNNyZ8.png)
* ![react creates element](https://i.imgur.com/6JCc8vU.png)
* ![class components vs hooks system chart](https://i.imgur.com/1CbdDlN.png)
* [part 1 of steps to get latitude to appear on screen in react class component](https://i.imgur.com/0EsaC0H.png)
* [part 2 of steps to get latitude to appear on screen in react class component](https://i.imgur.com/u32ny9z.png)
* ![conditional rendering if lat or error](https://i.imgur.com/NKhOPIl.pn) 
* ![component life cycle](https://i.imgur.com/B1hU7VM.png) 
* ![controlled component steps diagram](https://i.imgur.com/5d7KiMT.png)
* ![react AJAX diagram](https://i.imgur.com/VDbAdJF.png)
* ![diagram for react and dynamic images css grid](https://i.imgur.com/13X9clb.png)
  * `document.querySelector('img').clientHeight` - get height of image
  * we don't use vanilla JavaScript in React to grab DOM elements, we use the Ref hook
    * React Refs - gives access to a single DOM element
    * We create refs in the constructor, assign them to instance variables, then pass to a particular JSX element as `props`
    * Can we assign refs to state?
      * Yes, in theory we can assign refs to the state of our component but not really practical because these refs will not change over time and we will never all setState() with a ref (in general we only put data in state when we expect it to change over time)

### use async await syntax in react class component
```
class App extends React.Component {
  state = {
    images: [],
  };

 onSearchSubmit = async (term) => {
    const response = await axios.get(`https://api.unsplash.com/search/photos`, {
      params: { query: term },
      headers: {
        Authorization: 'Client-ID N5lZBvSduAroXytG62hsTFpsS4cCCiB3aWNpXgzZ6YU',
      },
    });
    console.log(this);
    this.setState({ images: response.data.results });
  };
```

### Why controlled components are preferred over uncontrolled forms
* In uncontrolled forms we can only gain access to the text inside the input is by going into the DOM and grabbing in 
* we did have a small period of time to grab the text in React when the user was typing into the input but during all other times the source of truth (aka source of data) was through the inside our HTML document and not inside our React component (this is important we as developers do not like to store information inside our HTML elements - we don't like to do that and instead we want to centralize all of the info we have inside our React component - that is what we want to strive for to insure our React side of our app is driving all the data that is going into our app and we are not going to somehow store data inside the DOM)

![uncontrolled diagram](https://i.imgur.com/svajEM9.png)

![here is a controlled react diagram](https://i.imgur.com/Soncl9H.png)

* now we can know at any given point in time we know what the value is in our form, we don't have to go over to the DOM and reference that input and pull the value out of it - instead we look directly at our React component and look at its state object and we can see the input value stored in the state object of that component

## map vs for loop
![for loop through array](https://i.imgur.com/R83ZmMt.png)
and this is so much easier and does same thing

```
const numbers = [1,2,3];
const newNumbers = numbers.map(n => n * 2);
newNumbers
```

## destructure array with useState
* this is less typing
* **note** no array is created here!
* called "array destructuring" and this is pure vanilla JavaScript

```
import React, { useState } from 'react';

const Accordion = ({ items }) => {
  const [activeIndex, setActiveIndex] = useState(null);

```
* than this (way more typing)

```
import React, { useState } from 'react';

const Accordion = ({ items }) => {
  const things = useState(null);
  const activeIndex = things[0];
  const setActiveIndex = things[1];
```
* notes about syntax

  `const [activeIndex, setActiveIndex] = useState(null);`
  
* activeIndex (name what you want but convention is whatever your active state name is you use setThatName for the function that will be used to update state which will re-render the component)
* when we call useState it takes in one argument which will be the default state

![diagram summing up destructuring arrays in React](https://i.imgur.com/VIrDaKi.png)

![diagram showing direct relationship between class based components state and functional components state](https://i.imgur.com/VIrDaKi.png)
* multiple pieces of state are different in class based components vs functional components

![diagram showing the difference](https://i.imgur.com/UKUvymo.png)

## Tools/Resources
* https://unsplash.com/oauth/applications/371971 (images API)
* https://babeljs.io/repl
* https://stephengrider.github.io/playgrounds/
