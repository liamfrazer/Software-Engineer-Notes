Date: 2023-02-17
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Reference: [JavaScript Mastery Pro][https://javascript-mastery.teachable.com/courses/849847/]
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

* JavaScript only hoists declarations, not initialisations
* If a variable is declared and initialised after using it, the value will be undefined
```JavaScript
console.log(num);
var num;
num = 6;
```
```console
undefined
```

* To avoid this pitfall, we would make sure to declare and initialise the variable before we use it
```JavaScript
function hoist() {
    var message = 'Hoisting is cool!'
    return message;
}

console.log(hoist());
```
```console
Hoisting is cool!
```
* The variable declaration `var message` whose scope is in the function `hoist()` is hosted to the top of the function

* Always declare variables exactly where they should be, at the top of the scope they're used in
* If they're declared correctly, they're always going to be predictable and we don't have to rely on hoisting

* `let` and `const` hoist but you cannot access them before the actual declaration is evaluated at runtime
* With `let` and `const` you get back exactly what you expect: a reference error
* This is JavaScript's way of letting us know we need to write clean code
* You should always declare variables before using them

```JavaScript
console.log(myVarString);
var myVarString = 'var';

console.log(myLetString);
let myLetString = 'let';

console.log(myConstString);
const myConstString = 'const';
```
```console
undefined
Uncaught ReferenceError: Cannot access 'myLetString' before initialisation
```

## Function Hoisting
* The same as `var` variables, the function declarations are hoisted completely to the top
* Always declare the function before you call it

```JavaScript
hoisted(); // 'This function has been hoisted.'

function hoisted() {
    console.log('This function has been hoisted.');

}
```
```console
This function has been hoisted.
```

### Function Expressions
* Constants and function expressions save us from doing that
* Function expressions are not hoisted
 ```JavaScript
functionExpression(); // ReferenceError
const functionExpression = () => console.log("Will this work?");
```
```console
Uncaught ReferenceError: Cannot access 'functionExpression' before initialisation
```



