Date: 2023-02-20
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Reference: https://javascript-mastery.teachable.com/courses/849847/
Tags: #ForEach #Map #Filter #Find #Includes #Sort #Some #Every #Reduce #Methods #Arrays 

---
# Array Complex Methods

## ForEach
* The `array.forEach` method performs an action for each element in the array
* The standard `for loop` can do the same, but the `array.ForEach` method can replace this
```JavaScript
let names = ['Liam', 'Michael', 'Frazer']
for (let i = 0; i < names.length; i++) {
    console.log(i, names[i]);
}
```
```console
0 'Liam'
1 'Michael'
2 'Frazer'
```
* In the example above, we have to declare and initialise another variable `i`
* Then the loop compares it every time with the `array.length` 
* If the expression evaluates to true, then only the loop executes
* After the loop body is executed, the value of `i` increments by one
* We can eliminate this process using `array.forEach` method

### Syntax for `array.forEach`
```JavaScript
array.forEach((value, index) => {
	// ...
});
```

```JavaScript
let names = ['Liam', 'Michael', 'Frazer'];

names.forEach((value, index) => {
    console.log(value, index);

});
```
```console
Liam 0
Michael 1
Frazer 2
```
* The first argument of the `forEach` method is the function that you want to execute for each element of the loop.
* This `callback function` can have two arguments.
* The first argument is the value of the current element the loop is on
* The second argument is the index of the current value

### Using a named function as a Call-back
```JavaScript
const names = ['Liam', 'Michael', 'Frazer'];

function logArrayElement(element, index) {
    console.log(element, index);
}

names.forEach(logArrayElement)
```
```console
Liam 0
Michael 1
Frazer 2
```
* You have to make sure that the order of the arguments in the predefined/named function used as the call-back is the same as the syntax requires

### Using an arrow function
```JavaScript
const names = ['Liam', 'Michael', 'Frazer'];
const logName = (name, i) => console.log(name, i);

names.forEach(logName);
```
```console
Liam 0
Michael 1
Frazer 2
```


### Return value of `array.forEach()`
* This method returns `undefined` and this method is not chainable
* You can't call one method after another on an array when using `forEach` method
* You cannot use cascading notation with `forEach method`
* This method is used to execute side effects at the end of the chain
* Such as logging all the elements in the array after performing a series of actions on the array

### Usage

#### Use When
1. Callback function is to be executed on every single element of the array
2. Improve performance (provided first condition is satisfied)

#### Don't use when
1. You want to stop or break the loop when some condition is true
2. For example, you want to console log elements of `myArray` but break the loop if the value of the current element is `X`. This is compulsorily to use the standard for loop to be able to do so
3. The callback function is asynchronous. Instead use the standard for loop

### Example
```JavaScript
let sum = 0;
const numbers = [65, 44, 12, 4]

numbers.forEach((number) => {
    sum += number;
});

console.log(sum); // 125
```

## Map
* `array.map` allocates memory in order to store and return values.
* `array.forEach` method does not allocate memory, so it doesn't store any returned values
* The `array.forEach` method also allows a callback function, that will allow you to change the original array
* `array.map` will instead return a new array while leaving the original one in its original state
```JavaScript
const inventory = [
    { price: 5, name: 'eggs' },
    { price: 10, name: 'ham' },
    { price: 15, name: 'mayo' },
    { price: 20, name: 'bread' },
];

const prices = inventory.map(item => item.price);

console.log(prices); // [5, 10, 15, 20]
```

```JavaScript
const inventory = [
    { price: 5, name: 'eggs' },
    { price: 10, name: 'ham' },
    { price: 15, name: 'mayo' },
    { price: 20, name: 'bread' },
];

const prices = inventory.map(item => item.price);
const items = inventory.map(item => item.name)

console.log(prices); // [5, 10, 15, 20]
console.log(items); // ['eggs', 'ham', 'mayo', 'bread']
```

## Filter
* The `array.filter()` method filters certain elements from an array.

### Example 1
```JavaScript
const numbers = [-10, 0, -2, 15, -36, 25] // Array of positive and negative numbers

const positiveNumber = numbers.filter((number) => {
    return number >= 0;
});

console.log(positiveNumber); // [0, 15, 25]
```

```JavaScript
const numbers = [-10, 0, -2, 15, -36, 25] // Array of positive and negative numbers
const positiveNumber = numbers.filter((number) => number >= 0);

console.log(positiveNumber); // [0, 15, 25]
```

### Example 2
```JavaScript

```


## Find

## Includes

## Sort

## Some and Every

## Reduce