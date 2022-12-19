# 01-objects-lesson
* no slides

## welcome - stoke curiosity
* f25 - how do you feel about the material so far?
* we are going to learn about a new structure to hold data (now that we learned about `variables` and `arrays`
* this structure will enable us to clean up our code
* this structure will make data much easier to access and manipulate

## Instructor - Objects (15 min)
`01-Ins-Objects/script.js` open in IDE
* objects are like real objects in real life
* they are things that have distinct `characteristics` aka `properties`
* let's create a planet object

### we use object literal notation to create the planet object
`var planet = {};`

* objects have many related properties that help define that object
* DO: show the planet object and it properties
* log the object

### sidebar
* console.log() and Math.random() - we used this already
* this is called `dot notation`
* we use this same dot notation to access object properties

`planet.name`

### bracket notation
* we can also access a value using `bracket notation`

`console.log(planet['name']);`

* dot notation is easier and you will use that most of the time but there are times when we would need to use `[bracket](bracket) notation`
* [source](https://frontend.turing.edu/lessons/module-1/js-dot-bracket-notation.html)
### Questions
Q: When would we want to use an object in JavaScript?
A: When we want to create an unordered collection of properties that describe a particular thing.
Q: How do we access a value stored in an object?
A: We use dot notation and bracket notation. Both use the object's name and the associated key.
Q: Where have we used bracket notation before?
A: We used bracket notation with arrays.

## Student: Objects (15 min)
`02-Stu-Objects/README.md`

## Instructor Review (10 min)
* F25 - how comfortable are you using objects?
* copy readme parts into `script.js` and walk through
* Make sure to review:
  * What is an object literal?
  * key-value pairs
  * dot notation

### bracket notation
```
// Bracket notation allows you to access properties with special characters in their names, while you can not do this with dot notation
let obj = {"foo.Bar": 2}
obj["foo.Bar"] // valid syntax
obj.foo.Bar //invalid syntax
```

### another example bracket notation
```
var phrases = {
    greeting: 'hello',
    departing: 'goodbye'
  }

  var lookupField = 'greeting';
// bad
console.log(phrases.lookupField); // undefined
console.log(phrases['lookupField'); // undefined
// good
console.log(phrases[lookupField); // undefined
```

### for in loop
```
for (let key in obj) {
  console.log(obj[key]);
}
```

### Questions
* Q: How are key-value pairs used in objects?
* A: The key is a unique identifier used to access the value. In objects, key-value pairs define the properties of an object

### Dig into the Documentation
[MDN Web docs on objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
## Instructor - Object Methods - 10 min
* JavaScript has some code "built-in" to it
  * examples: `console.log()` and `Math.random()`
  * Q: what do we call these?
  * A: `methods`

### What are methods?
* Named pieces of code that perform a certain function
  * console.log() prints to the console
  * Math.random() generates a random number
* The only part of `console.log()` and `Math.random()` that are methods are `log()` and `random()`
  * `console` and `Math` are `objects`

#### Objects also have "built-in` methods
* Let's talk about 3 of them:
  * `.keys()`
  * `.values()`
  * `.entries()`
* Q: What do you think the three methods above do?

### `03-Ins-Object-Methods/script.js`
```
// Creates an array of the keys of the object
console.log(Object.keys(planet));

// Creates an array of the values of the object
console.log(Object.values(planet));

// Creates an array containing each key-value pair as an array
console.log(Object.entries(planet));
```

#### Q: why are they on the Object object?
* A: Each object is based upon the `Object` data type and in order to use these built-in methods on a custom object, we must use this syntax
  * Q: How are key-value pairs used in objects?
    *A: The key is a unique identifier used to access the value
           In objects, key-value pairs define the properties of an object      

## Student: Object Methods (15 min)
* `04-Stu-Object-Methods/README.md`

## Instructor Review: Object Methods
* menu with drinks as keys and prices as values
* Object.keys for first part
  * `console.log('The menu contains the following drinks:', Object.keys(menu));`
* use Object.values to store the array, total var initiated with 0 value
  * then use a for loop to total up all the prices
  * Object.keys(menu));
    * `console.log('Total Menu Cost = $' + total);`

```
// Our Menu object
var menu = {
  coffee: 4.50,
  latte: 6.50,
  coldBrew: 6,
  matcha: 7
};

// We assign our menu values to the prices variable
var prices = Object.values(menu);

// Instantiate the total
var total = 0;

// We print the entire menu
console.log('The menu contains the following drinks:', Object.keys(menu));

// We loop through the values and add them to the total
for (let i = 0; i < prices.length; i++) {
  total += prices[i];
}

// We print the total cost
console.log('Total Menu Cost = $' + total);
```


### bonus
```
var pricesArr = Object.values(menu);
var total = 0;
for (var properties in pricesArr) {
  total += pricesArr[properties];
}
console.log(total);
```
* [source](https://stackoverflow.com/questions/1230233/how-to-find-the-sum-of-an-array-of-numbers)

## 15 minute break

## Instructor - Objects vs Arrays (10 min)
* We are storing data using Objects and Arrays
* Is one better? 
  * Both can store many items
  * We can manipulate and change both
* Q: Which one should we use?
* A: It depends

### Objects
* should be used to represent specific things
  * cars
  * planets
  * users
  * bank accounts
  * game characters
  * lots of more examples but I think you get the idea

```
var planet = {
  name: "Earth",
  age: "4.543 billion years",
  moons: 1,
  isPopulated: true,
  population: "7.594 billion"
}
```
* These items have multiple properties that are all different, but represent that thing (planet in this case)

### Arrays
* Should be used whenever we want to store many items of the same type in a single variable
* **note** JavaScript allows us to store different types inside an array but the best practice is to keep your arrays consistent
  * an array of strings
  * an array of numbers
  * an array of other arrays
  * or even... an array of objects `example: https://jsonplaceholder.typicode.com/todos/`

## Instructor - Nested Data Structures (15 mins)
`05-Ins-Nested-Data/script.js`

* We can nest data structures inside of each other
  * Gives us the ability to have robust data structures
  * And also store lots of data
* Examples of data structures
  * Arrays of arrays (use format to make this more easy to see)
  * Objects of Objects (discuss way to make code more readable here - this is a programming concept where an object is made up of other objects)
  * Array of Objects
  * Objects of Arrays

### Q: In interest of making our code more readable - how would we create these nested structures
* A: declare our objects and arrays first, then nest them afterward
* comment out other code and comment in new code
* Q: why does logging the array print the brackets but when you use `+` to concatenate a string and an array, there are no brackets?
* A: the array is internally converted to a string using the `toString()` method (this converts every array member to a string and puts commas between them) - [source](https://www.codecademy.com/forum_questions/505b3bfc68701a00020177f0)
## Student: Nested Data Structures (15 min)
* You will be using the concept we discussed of `composition` in this exercise

## Instructor Review: Nested Data Structures (10 min)
* f25 - how comfortable do you feel about nested data structures?
* Walk through this code - look at the solution and type it

### Topics to review
* Array of Objects
* Composition
* `06-Stu-Nested-Data/solved/script.js`

```
// We must declare these objects first in order for our Menu object to render properly.
var sizes = ['small', 'medium', 'large'];

var milks = ['2%', 'Whole', 'Oat', 'Coconut', 'Soy'];

var coffee = {
  name: 'Coffee',
  price: 4.50,
  sizes: sizes,
  isIced: false,
  withSugar: false
}

// Notice we added new properties to this object
var latte = {
  name: 'Latte',
  price: 6.50,
  sizes: sizes,
  isIced: true,
  withSugar: true,
  milks: milks
}

// This object only has a few properties based on what it needs
var coldBrew = {
  name: 'Cold Brew',
  price: 6,
  sizes: sizes,
  withSugar: false
}

var matcha = {
  name: 'Matcha Latte',
  price: 7,
  sizes: sizes,
  isIced: true,
  withSugar: false,
  milks: milks
}

var drinks = [coffee, latte, coldBrew, matcha];

// Our Menu object
var menu = {
  drinks: drinks,
  // Here we declared the array within the object since we were not using this array elsewhere.
  food: ['Bagel', 'Danish', 'Muffin'],
  // We included the milk options and size options in this object as well. We are thinking ahead to a point where we might need to simply print the options (such as to a webpage), rather than choose an option within a drink when it is ordered.
  milks: milks,
  sizes: sizes
};

console.log('The price of a coldBrew is: $' + menu.drinks[2].price);
console.log('The price of a latte and a coffee is: $' + (menu.drinks[1].price + menu.drinks[0].price));
console.log('You can choose from the following milk options: ' + menu.milks);
console.log('You can choose from the following size options: ' + menu.sizes);
```

### Tips
* psuedocoding is quite useful here
* we can think about what properties we need and what each property contains
* students share structures in slack
* now that we know what structure our object will have, we can determine what other structures we may need
* Tell students - there is really no right or wrong way here, as long as you follow the `Acceptance Criteria`
* walk through code - say it is composition i am using in the solution - a programming concept where an object is made up of other objects
* order is important ['small', 'medium', 'large']

## We do - Looping Nested Data Structures (10 mins)
* let's assume oat milk is $1 extra
* we will use the same menu object we used before
* But we want to loop through nested data:
  * loop through all the drinks (think of us wanting to output this on our coffee web page)
  * loop through the drinks and inside that loop, (check for a specific drink "matcha latte" using if logic) and then loop through all the milks and if logic again to see if 'oak milk' is a match and if it is add a dollar to the the price of the matcha latte and print the price out
  * the rest of the code we already did in the previous exercise





















