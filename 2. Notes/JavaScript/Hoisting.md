Date: 2023-02-17
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Tags: #Hoisting

---
# Hoisting
* Hoisting is a JavaScript mechanism where variables and functions declarations are moved to the top of their scope before code execution
* No matter where functions and variables are declared, they're moved to the top of their scope, regardless of whether their scope is global or local
* When JavaScript compiles all of your code, all variable declarations using `var` are hoisted/lifted to the top of their functional (if declared inside a function)
* Or to the top of their global scope (if declared outside of a function) regardless of where the actual declaration has been made

## Variable Hoisting
* An undeclared variable is assigned the value `undefined`  at execution and also the type `undefined`
* The key thing to note in regards to hoisting is that the only thing that gets moved to the top is the variable declaration, not the actual value given to the variable
```JavaScript
console.log(myString);

var myString = 'test'
var myString;

console.log(myString);
myString = 'test';
```
```console
undefined
test
```

```JavaScript
var hoist;

console.log(hoist);

hoist = 'This variable has been hoisted'
```
```console
undefined
```

```JavaScript
function hoist() {
    var message;
    console.log(message);
    message = 'hoisting is cool'
}

hoist();
```
```console
undefined
```


## Function Hoisting


