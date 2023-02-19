Date: 2023-02-17
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Reference: [JavaScript Mastery Pro][https://javascript-mastery.teachable.com/courses/849847/]
Tags: #Scope #Global #Local #Block

---
# Scope

* Scope simply allows us to know where we have access to our variables
* It shows us the accessibility of variables, functions and objects in particular parts of the code
* It provides us with some level of security to our code
* It helps to improve efficiency, track bugs and reduces them
* It also solves the problem of naming variables
* Variables defined inside a function are in local scope
* Variables defined outside of a function are in global scope
* Each function when invoked creates a new scope
* You can usually search for the closest { and } braces around where you define the variable
* The { and } is the block of code's scope

## What is more useful
* The local and global variables are equally important while writing a program in any language
* A large number of the global variables may occupy a huge amount of memory
* An undesirable change to global variables will become tough to identify
* It is advisable to avoid declaring unwanted global variables
* Always declare variables in the scope that you want to use them in

## Key Difference
* Local variables are declared inside a function
* Global variables are declared outside the function

* Local variables are created when the function has started execution and are lost when the function terminates
* Global variables are created as execution starts and are only lost when the program ends

* Local variables don't provide data sharing
* Global variables provide data sharing

* Local variables are stored on the stack
* Global variables are stored on a fixed location decided by the compiler

* Parameters passing is required for local variables
* Parameter passing is not necessary for a global variable

## Global scope
* When you start writing in a JavaScript document, you're already in the Global scope
* Variables written inside the Global scope can be accessed by and altering in any other scope
```JavaScript
const name = 'Liam'
```
```JavaScript
const logName = (name) => {
    console.log(name);
}

logName();
```

### Global Scope Advantages
* You can access the global variable from all the functions or modules in a program.
* It is ideally used for storing "constants" as it helps you keep the consistency
* A Global variable is useful when multiple functions are accessing the same data

### Global Scope Disadvantages
* Too many variables declared as global, then they remain in the memory till program execution is completed, this may cause an "out of memory" issue
* Data can be modified by any function. Any statement written in the program can change the value in the global variable. This may give us unpredictable results in multi-tasking environments
* If global variables are discontinued due to code refactoring, you will need to change all the modules where they are called.

## Local Scope
* Variables defined inside a function are in the local scope
```JavaScript
// Global Scope
const someFunction = () => {
    // Local Scope#1
    const anotherFunction = () => {
        // Local Scope #2
    }
}
```

### Local Scope Advantages
* The use of local variables offer a guarantee that the values of variables will remain intact while the task is running
* You can give local variables the same name in different functions because they are only recognised by the function they are declared in
* Local variables are deleted as soon as any function is over, they release the memory space which it occupies.

### Local Scope Disadvantages
* They have a very limited scope.
* There isn't necessarily a disadvantage, but if you ever find yourself needing to use that variable in a parent scope, just declare it in a parent scope, as seen in the example below:

```JavaScript
const someFunction = () => {
    // Local Scope#1
    const anotherFunction = () => {
        // Local Scope #2
    }
}
```
* If you need to use a variable only inside the `anotherFunction` function, just declare it there.
* If for some reason, you need to use it both in the `someFunction` & `anotherFunction` functions, declare it in the `someFunction` scope
* If you need to use the variable everywhere, declare it in the global scope

## Block Scope (only `let` & `const`)
* Block statements like `if`, `for` and `while` loops, unlike functions don't create a new scope
* Variables defined inside of a block statement will remain in the scope they were already in
```JavaScript
if (true) {
    // This `if` conditional block doesn't create a scope
    var name = 'Liam' // name is still in the global scope
}
console.log(name);
```
```console
Liam
```
* That is only true with `var`
* Variables defined with `const` & `let` have something called a Block scope
* That means that they will be available only inside of the block of code you create them in
```JavaScript
if (true) {
    // This `if` conditional block doesn't create a scope

    // name is in the global scope because of the `var` keyword
    var name = 'Liam' // name is still in the global scope
    // likes is in the local scope because of the `let` keyword
    let likes = 'coding';
    // skills is in the local scope because of the 'const' keyword
    const skills = 'JavaScript';
}

console.log(name); // logs 'liam'
console.log(likes); // likes is not defined
console.log(skills); // skills is not defined
```
```console
Liam
Uncaught ReferenceError: likes is not defined
```
