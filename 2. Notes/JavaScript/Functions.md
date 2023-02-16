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


## Function Return


## Arrow Functions


## Parameters vs Arguments


## Scope


## Hoisting


## Closures

