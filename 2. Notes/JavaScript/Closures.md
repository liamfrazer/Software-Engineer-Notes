Date: 2023-02-17
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Reference: https://javascript-mastery.teachable.com/courses/849847/
Tags: #Closures

---
# Closures
* A closure gives you access to an outer function's scope, from an inner function
* In JavaScript, closures are created every time a function is created, at function creation time

```JavaScript
const outer = () => {
    const outerVar = 'Hello'

    const inner = () => {
        const innerVar = 'Hi'
        console.log(innerVar, outerVar);
    }
    return inner;
}

const innerFN = outer(); // Closure, because we have access to the variables of the parent scope

innerFN();
```
```console
Hi Hello
```

```JavaScript
const init = () => {
    const hobby = "Learning JavaScript"; // Hobby is a local variable created by init
    const displayHobby = () => { // displayHobby() is the inner function, a closure
        console.log(hobby); // using variable declared in the parent function
    }
    displayHobby();
}

init();
```
```console
Learning JavaScript
```
* `init()` creates a local variable called `hobby` and a function called `displayHobby()`.
* The `displayHobby` function is an inner function that is defined inside `init()`
* This is only available within the body of the `init()` function
* The `displayHobby` function has no local variables of its own
* However, since inner functions have access to the variables of outer functions, `displayHobby()` can access the variable `hobby` declared in the parent function `init()`

