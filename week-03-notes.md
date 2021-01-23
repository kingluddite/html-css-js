1995 Brendan Eich created JavaScript in 10 days

- [link to article on Brendan Eich](https://thenewstack.io/brendan-eich-on-creating-javascript-in-10-days-and-what-hed-do-differently-today/)
  JavaScript is not Java
- test

## Script element

https://repl.it/@kingluddite/javascript-week-03-lecture#01-script-element.html

## Difference between var, const and let

[link to examples](https://github.com/kingluddite/catchup-05-react-es6/blob/00-var-variables/index.js)

## Understanding Scope

- Definition of Scope
  - Scope is a context, or region of code, in which a variable exists and can be accessed

### JavaScript has "lexical scope"

- This means the scope of a variable depends where it was declared

### Two types of Scope

- global
- local
  - block scope
    - let
    - const
  - function scope
    - var

### What is a code block?

- Any set of statements executed as part of a
  - function definition
  - if
  - switch
  - while
  - do...while loop
  - for loop
  - tip: Anything inside curly braces is "block scope"

### What is global scope?

- Variables declared outside any code block have global scope (they are available everything)
- best practice - don't pollute the global scope
  - Leads to variable conflicts

### What is function scope?

- Local scope (similar to block scope but only applies to function blocks)
- Issued by variables using pre ES6 var keyword
  - [what is ES6?](https://medium.com/@hossam.hilal0/what-is-es6-1d860c4dacf8)
  - [what is babeljs?](https://www.youtube.com/watch?v=yLrNwo4wXOs)

### Code examples of scope

[link to code example of scope](https://github.com/kingluddite/catchup-05-react-es6/blob/03-scoping/index.js)

## conditional statements

- aka "if" statements
- Represent a fork in a path
- Program meets a conditional statement and evaluates

![if else diagram](https://i.imgur.com/9pd4cTV.png)

```javascript
let greeting;
if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

### What is a code block?

- An else is not required
- Boolean values
- Truthy/Falsy

## = vs == vs ===

- `=` assignment operator
- `==` abstract comparison operator
- `===` strict comparison operator

```javascript
var foo = 13;
var bar = 13;

console.log(foo == bar); // true
console.log(foo === bar); // also true
```

### What is the difference between `==` and `===`?

- == converts the variable values to the same type before performing comparison
  - **note** This is called type coercion.
- === does not do any **type conversion** (coercion) and returns true only if both values and types are identical for the two variables being compared

```javascript
var oneNumber = 1;
var oneNumberAgain = 1;
var oneString = "1"; // note: this is string

console.log(one == oneNumber); // true
console.log(one === oneNumberAgain); // true
console.log(one == oneString); // true. See below for explanation.
console.log(one === oneString); // false. See below for explanation.
```

## Truthy vs Falsy

- Boolean has two values:

  1. True
  2. False

* But values can be converted to other data types (coercion)
  - A Number to a String
  - A String to a Number
  - A Boolean to a Number

### Truthy is:

- When a non-Boolean value is converted (through coercion) to a Boolean true

### Falsy is:

- When a non-Boolean value is converted (through coercion) to a Boolean false

### How does JavaScript determine if a value is truthy or falsy?

- All these values are falsy
  - false
  - undefined
  - 0
  - null
  - NaN (Not A Number)
  - An empty string "" (or '' or backtics)

### What will the following code execute?

```javascript
let greeting;

if (null) {
  greeting = "Good morning";
} else if (20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

- [read more on truthy and falsy](https://www.sitepoint.com/javascript-truthy-falsy/)

* Many times you will not check for a match but whether it is just truthy or falsy
  - example: Check if there was text entered for a form field validation (you want a user to enter their name)

```javascript
const firstName = "Jane";
if (firstName) {
  console.log("You have a firstName");
} else {
  console.log("You didn't enter a first name");
}
```

## Operators and Operands

- The values in an operation are called `operands`
- One JavaScript operator is the assignment operator: `x = 5;`

### Binary operator (left and right operands - most common)

`const name = 'Joe'`

### Unary operator (one operand)

`count++`

### Ternary operator

```javascript
let isMember = "$2.00";
isMember ? "$2.00" : "$10.00";
```

### Remember the order of operator precedence

- [read more](https://www.purplemath.com/modules/orderops.htm)
- "PEMDAS"
- "Please Excuse My Dear Aunt Sally"
- "Parentheses, Exponents, Multiplication and Division, and Addition and Subtraction"

## You can use multiple operators

- add (+)
- subtract (-)
- multiply (\*)
- divide (/)
- And using multiple `x = y + 3 * 5`

## Lots of different types of Operator categories

- Comparison Operators
- Logical Operators
- Assignment Operators
- Arithmetic Operators
- String Operators
- And more

## Code Challenge: Switch

[codepen](https://codepen.io/minae/pen/xxwdxmV?editors=0011)

```javascript
function getMembershipPerks(mLevel) {
  switch (mLevel) {
    case "gold":
      console.log("Unlimited Free Plays");
    case "silver":
      console.log("VIP Room Access");
      break;
    case "bronze":
      console.log("VIP Room Access on Weekdays");
      break;
    default:
      console.log("Invalid membership level");
  }
}

getMembershipPerks("gold");
```

## Operators

## While Loops

```javascript
let i = 0;
while (i < 5) {
  i += 1;
  console.log("This is iteration #" + i);
}
```

### do while loops

```javascript
// do while loop (always will run at least once)
let i = 5;
do {
 i += 1;
 console.log(`This is iteration #${i}`);
}
```

### other do while example

```javascript
let answer = "";
do {
  answer = prompt("Do you like chocolate?");
} while (answer !== "yes");
```

## Arrays

### What are arrays?

- Arrays are numerically indexed collections of values

#### Arrays can contain:

- Strings
- Numbers
- Booleans
- Other arrays

### Create an array

- Use the "array literal syntax"
- To use an array more than once assign it to a variable

### Access array items

- Array indexes start at 0 (zero)
- Access an item in an array using "bracket notation"

```javascript
const team = ["Mike", "Mary", "Joe", "Jane"];
const playerMike = team[0];
```

### Modify array items

### length of an array

- Property of Array
- Array length starts at 1
- Getting last item in an array `team[team.length - 1];`

### Array methods

- Built-in JavaScript array functions (called array methods)
- `arrayName.methodName()`
- Read MDN documentation for array methods
  - Some array methods have parameters (some do not)
  - Most array methods return a value
  - Some array methods are "mutatators" (then mutate (aka change) the array)
  - others are not (it is important to know which are mutators and which are not)
    - [more info on mutate vs non-mutate](https://lorenstewart.me/2017/01/22/javascript-array-methods-mutating-vs-non-mutating/)
  - [review pop() array method documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)

#### push()

- **What it does** Adds one or more elements to the end of an array
- **returns** the length of the array

```javascript
const carCompanies = ["bmw", "vw", "ford"];

console.log(carCompanies.push("tesla"));
// expected output: 3

console.log(carCompanies);
// expected output: Array ['bmw', 'vw', 'ford', 'testla']
```

#### pop()

- **What it does** Removes the last element from an array
- **returns** Returns the element removed

```javascript
const usStates = ["pa", "wa", "fl", "tx"];

console.log(usStates.pop());
// expected output: "tx"

console.log(usStates);
// expected output: ["pa", "wa", "fl"];

usStates.pop();
usStates.pop();

console.log(usStates);
// expected output: ["pa"];
```

#### shift()

- **What it does** Removes the first element from an array
- **returns** The removed element

```javascript
const groceries = ["eggs", "milk", "bread"];
const firstItem = groceries.shift();

console.log(groceries.shift());
// expected output: ["milk", "bread"]

console.log(firstItem);
// expected output: "eggs"
```

#### unshift()

- **What it does** Adds one or more elements to the beginning of an array
- **returns** the length of the array

```javascript
const array1 = [1, 2, 3];

console.log(array1.unshift(4, 5));
// expected output: 5

console.log(array1);
// expected output: Array [4, 5, 1, 2, 3]
```

#### join()

- **What it does** Creates and returns a new string by concatenating all of the elements in an array

```javascript
const elements = ["Fire", "Air", "Water"];

console.log(elements.join());
// expected output: "Fire,Air,Water"

console.log(elements.join(""));
// expected output: "FireAirWater"

console.log(elements.join("-"));
// expected output: "Fire-Air-Water"
```

#### includes()

- **What it does** Determines whether an array includes a certain value amount it's items
- **returns** true or false as appropriate

```javascript
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// expected output: true

const pets = ["cat", "dog", "bat"];

console.log(pets.includes("cat"));
// expected output: true

console.log(pets.includes("at"));
// expected output: false
```

#### indexOf()

- **What it does**
- **returns** the first index at which a given element can be found in the array (or -1 if it is not present)

```javascript
const beasts = ["ant", "bison", "camel", "duck", "bison"];

console.log(beasts.indexOf("bison"));
// expected output: 1

// start from index 2
console.log(beasts.indexOf("bison", 2));
// expected output: 4

console.log(beasts.indexOf("giraffe"));
// expected output: -1
```

## Generating Random Numbers

- Built-in in global object in JavaScript call Math (notice the capital "M" in Math)

### Math.random()

- Generates a random number between 0 and 1
- The potential value of this number includes 0 but not 1

`const randomNum = Math.random()`

- To generate a random number between 1 and 100 `Math.random() * 100`

### Math.floor()

- If you want a number with no decimals then just round it down

`const pi = Math.floor(3.14); // 3`

### Combine them

`const randomNum = Math.floor(Math.random() * 6)`

### Generator a number between 1 and 100

- Add 1

`const randomNum = Math.floor(Math.random() * 100) + 1;`

## 4. Exercise: Number Guessing Game

![guessingGame](https://i.imgur.com/KqbUQXm.png)

### HTML file has this fragment in the body

```html
<button type="button" onclick="runGame()">Start</button>
```

### pseudocode

```javascript
function runGame() {
  let guessString = "";
  let guessNumber = 0;
  let correct = false;
  let numberOfTries = 0;

  // Generate a random number between 1 and 10
  const randomNumberTarget = Math.floor(Math.random() * 10) + 1;
  // keep asking player question over and over again (great for a while loop)
  do {
    // Get guess from player
    // store player guess in variable
    guessString = prompt(
      "Guess a number between 1 and 10.\n\n If you guess it that will be great!"
    );
    if (guessString === null) {
      return;
    }
    // convert string to number
    guessNumber = +guessString;
    // track the number of tries
    numberOfTries += 1;
    // check if guess a number?
    correct = checkGuess(guessNumber, randomNumberTarget);
    // if player guess not a number, warn player
  } while (!correct);
  console.log(
    "Correct Guess! The number was " +
      randomNumberTarget +
      ".\n\nIt took you " +
      numberOfTries +
      " tries to guess the correct number"
  );
}

function checkGuess(guessNumber, target) {
  let correct = false;

  if (isNaN(guessNumber)) {
    console.log(
      "You did not guess a number. Please guess a number between 1 and 10"
    );
  } else if (guessNumber < 1 || guessNumber > 100) {
    console.log("Please enter a number between 1 and 10");
  } else if (guessNumber > target) {
    console.log("too large");
  } else if (guessNumber < target) {
    console.log("too small");
  } else {
    correct = true;
  }
  return correct;
}
```

- **talking point** code readability vs brevity
- "write ugly code first then refactor"
- prompt() always returns a string
- **best practice** define variables or they will be `undefined`
- **tip** `typeof` great way to test the variable type
- escape character `\`
- escape sequence `\n\n` (2 new lines)

## Challenge Questions

- advanced array functions
  - [link to array functions](https://github.com/kingluddite/catchup-05-react-es6/blob/10-es6-functions/index.js)
