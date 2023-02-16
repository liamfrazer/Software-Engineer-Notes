Date: 2023-02-15
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Tags: #Functions #Declaring #Invoking #Arrow #Parameters #Argfuments

---
# Functions

* A function is a special value with one purpose
* A function represents some code in your program
* Functions come in handy if you need to execute the same code multiple times, without having to re-write it
* Calling a function such as `sayHi()` tells the computer to run the code inside it
* Once the code has been ran, it will then go back to where it was in the program
* Functions can be defined in multiple ways, with slight differences in how they function

## Defining functions
```JavaScript
function square(number) {
    return number * number
}
```
* `function` is the reserved JavaScript keyword for creating a function
* `square` is the name of the function, this can be customised to whatever our requirement is
* Inside the parentheses we have parameters
* Parameters are values we're going to send to our function when calling it
* The function `square` takes one parameter, called `number`
* Names of parameters do not matter, these can be customised
* The curly brace represents the start of the function block
* Everything else up to the closing curly brace represents the function body
* Within the function body, we can create variables, operators, add if/else statements etc
* This example function consists of one statement that returns the parameter of the function, which is `number` x `number`
* To retrieve values from a function, we need to call them

## Calling Functions
* Defining a function does not execute it
* Defining it simply names the function, then specifies what it does once called
* Calling the function actually performs the specified actions with the indicated parameters
```JavaScript
square(5);
```
* In the above code, we have the function name followed by parentheses
* Within the parentheses we include arguments
* Arguments are the values we want to fill our parameters with
* In the example above, we're sending the value of 5
* Within the above function, the parameter called number in the function declaration is going to become the number 5
* We then multiply it by itself, then return it
* This will return the result `25`
* To use the value from the function, we can store this in a variable
```JavaScript
const result = square(5);

function square(number) {
    return number * number
}

console.log(result);
```



## Declaring and Invoking Functions

* There are three different ways that we can declare a function within JavaScript

### Function Declaration
*  A function declaration defines a named function
* To create a function declaration, you use the function keyword followed by the name of the function
```JavaScript
function name(parameteres){
	statements
}
```

### Function Expression
* A Function expression defines a named or anonymous function
* An anonymous function is a function that has no name
* Within the function below, we are setting the anonymous function object equal to a variable
```JavaScript
let name = function(parameteres){
	statements
}
```

### Arrow Function Expression
* An arrow function expression is a shorter syntax for writing function expressions
* Arrow functions are the most modern way to create JavaScript functions
```JavaScript
const name = (parameters) => {
	statements
}
```

* For the majority of cases, we would always use the arrow functions
* The only exception to this is when we want to access the `this` keyword, which only a Function Declaration has access to

### Invoking Functions
* Functions execute when they are called
* This process is known as invocation
* You can invoke a function by referencing the function name, followed by an open and closed parenthesis
```JavaScript
function sayHi(name) {
    console.log(`Hi, ${name}`);
}

sayHi('Liam');
```
```console
Hi, Liam
```
* First we define the function named `sayHi`
* This function then takes one parameter `name`
* When executed, the function will log that `name` back to the console
* To invoke the function, we call it.
* We pass through a singular argument, in the example above we're calling the function with the `name:` `liam`

## Function Return
* Every function in JavaScript returns `undefined` unless otherwise specified
* If we don't tell the function to return, it is always going to return undefined
```JavaScript
function add(a, b) {
    return a + b;
}

const sum = add(2, 2);

console.log(sum);
```
```console
4
```
* This is a function that will return the sum of numbers `a` and `b`
* We then invoke the function and save the return value to the variable `sum`
* We then print the value with `console.log(sum)`

```JavaScript
function test() {
    return true;
    return false;
};

console.log(test());
```
```console
true
```
* The first return statement above immediately stops execution of our function
* This causes our function to return `true'
* The code `return false` is never executed

```JavaScript
function test() {
    console.log(1);
    return true;
    console.log(2);
    return false;
    console.log(3);
};

console.log(test());
```
```console
1
true
```
* In the above code, we only see the first console log and the return of true
* As soon as the function returns something, it has completed and returns back to where the function was originally called


## Arrow Functions


## Parameters vs Arguments


## Scope


## Hoisting


## Closures

