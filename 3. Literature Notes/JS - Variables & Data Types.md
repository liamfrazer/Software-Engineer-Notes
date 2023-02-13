Date: 2023-02-13
MOC: [[JavaScript]]
Tags: #JavaScript #Variables #Datatypes
Type: [[Literature Note]]

---

# Variables

* Variables are containers that hold re-useable storage

```javaScript
var variableName = "Welcome to Variables";
console.log(variableName);
```

* After ES6 we now have two new ways to declare a variable
* `let` is the preferred way of creating variables in modern JavaScript
* `const` is another variable typed assigned to data and the value cannot and will not change throughout the script.

```JavaScript
let variableName = "Welcome to Variables";
const variableName = "Welcome to Variables";
```

## Reassigning Variables
*  `const` values cannot be reassigned
```JavaScript
let variableName = "Welcome to Variables";
variableName = 'Hello!';
console.log(variableName);
```

## Creating an identifier (variable) in JavaScript
* The identifier must be unique - Identifiers cannot be declared twice.
* The name of the identifier cannot be a reserved keyword.
	* `var`
	* `let`
	* `const`
	* `function`
* The first letter must be a letter, $ sign or underscore - Any other special character will cause an error

# Data Types
## Primitive Datatypes
```JavaScript
// Primitive data types
let stringType = "This is the string data type";
let numberType = 1;
let booleanType = true;
let nullType = null;
let undefinedType = undefined;
```
* Only Objects are regarded as complex data types
* Objects are the most important data-type and form the building blocks for modern JavaScript

* Strings contain text values
* Numbers contain numbers
* Booleans contain `true` or `false`
* Null is only null, null specifies that we have a container to store a value in, but that value is non-existent
* Undefined means we don't have a variable or a value, this doesn't exist

## Comments
* Two types of comments; Single line, Multi-line
```JavaScript
/* 
multi line comment 
*/ 

// single line comment`
```

## Strings
* `String` is just a sequence of characters
* A `String` is a data type used to represent text.
* In JavaScript, there are 3 types of quotes
	* Single quotes
	* Double Quotes
	* Backticks
* Single and Double quotes are 'simple' quotes, practically no difference between them in JavaScript.
* Backticks are known as 'extended functionality quotes'.
	* Backticks allow us to embed variables and expressions into a string, by wrapping them with `${...}`

```JavaScript
const singleQuotes = 'Hello';
const doubleQuotes = "Hello";
const backticks = `Hello ${2 + 2}`;
```

## typeof
* When inspecting data types within JavaScript, we can write `typeof` before the value.
* This will give us a data type of the actual value
```JavaScript
const backticks = `Hello ${2 + 2}`;
console.log(typeof backticks);
```
```JavaScript
string
```

## Numbers
*  Within JavaScript, you don't have to specify the type of number (integer or a float), this is taken care of by the language's runtime environment.
```JavaScript
const wholeNumber = 5;
const decimalNumber = 0.5;
```
* There are many operations for numbers;
	* Multiplication = `*`
	* Division = `/`
	* Addition = `+`
	* Subtraction = `-`
```JavaScript
// Numbers
const firstNumber = 5;
const secondNumber = 10;
const result = firstNumber + secondNumber;
console.log(result);
```
```JavaScript
15
```

## NaN
* `NaN` stands for Not a Number, which represents a computational error.
* It is a result of an incorrect or an undefined mathematical operation.
```JavaScript
// Numbers
const firstNumber = "test";
const secondNumber = 10;
const result = firstNumber / secondNumber;
console.log(result);
```
```JavaScript
NaN
```

## Booleans
* Booleans represents a logical entity which can only equal the following;
	* `true`
	* `false`
* This is important for adding logic to our programs, which just two values we can create complex systems of loops and conditions
```JavaScript
// is Cool
const isCool = true;
if (isCool) {
    console.log('Cool');
} else {
    console.log('Not cool');
}
// Age
const age = 20;
if (age >= 18) {
   console.log("You may enter");
}
```
```JavaScript
Cool
You may enter
```
