Date: 2023-02-17
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
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


## Block Scope (only `let` & `const`)
