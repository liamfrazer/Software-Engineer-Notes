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
* An equivalent of a filter is a `for` loop with an `if statement`

### Example 1

#### Named Function
```JavaScript
const numbers = [-10, 0, -2, 15, -36, 25] // Array of positive and negative numbers

const positiveNumber = numbers.filter((number) => {
    return number >= 0;
});

console.log(positiveNumber); // [0, 15, 25]
```

#### Arrow Function
```JavaScript
const numbers = [-10, 0, -2, 15, -36, 25] // Array of positive and negative numbers
const positiveNumber = numbers.filter((number) => number >= 0);

console.log(positiveNumber); // [0, 15, 25]
```

#### For loop equivalent
```JavaScript
const numbers = [-10, 0, -2, 15, -36, 25] // Array of positive and negative numbers
const positiveNumbers = [] // Empty array to push For Loop results into

for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] >= 0) {
        positiveNumbers.push(numbers[i])
    }
}

console.log(positiveNumbers); // [0, 15, 25]
```


### Example 2

#### Filter & For loop
```JavaScript
// A startup wants to reward the employees with 7 or more hours of overtime

const employeesData = [
    { name: "Sebastian", overtime: 5 },
    { name: "Cardi Vee", overtime: 10 },
    { name: "George Lopez", overtime: 12 }
];

const goodEmployee = employeesData.filter((employee) => employee.overtime >= 7);
const employeeNames = []

for (let i = 0; i < goodEmployee.length; i++) {
    employeeNames.push(goodEmployee[i].name);
};

console.log(employeeNames); // ['Cardi Vee', 'George Lopez']
```

#### Filter & Map
```JavaScript
const employeesData = [
    { name: "Sebastian", overtime: 5 },
    { name: "Cardi Vee", overtime: 10 },
    { name: "George Lopez", overtime: 12 }
];

const goodEmployee = employeesData.filter((employee) => employee.overtime >= 7);
const employeeNames = goodEmployee.map((employee) => employee.name);

console.log(employeeNames); // ['Cardi Vee', 'George Lopez']
```

#### Filter, Map & ForEach
```JavaScript
const employeesData = [
    { name: "Sebastian", overtime: 5 },
    { name: "Cardi Vee", overtime: 10 },
    { name: "George Lopez", overtime: 12 }
];

const goodEmployee = employeesData.filter((employee) => employee.overtime >= 7);
const employeeNames = goodEmployee.map((employee) => employee.name);
employeeNames.forEach((name) => console.log(`${name} received an award`));
```
```console
Cardi Vee received an award
George Lopez received an award
```

## Find
* The `array.find` method for arrays returns the first value that matches its condition
#### Example 1
```JavaScript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const value = numbers.find((number) => number > 5);
console.log(value); // 6
```

#### Example 2
```JavaScript
const states = ['Alaska', 'California', 'Colorado', 'Hawaii'];
const state = states.find((state) => state.startsWith('C'));
console.log(state); // California
```

## Includes
* The `array.includes()` method checks if an array contains a certain value
* This will then return the Boolean `true` or `false` 
* `array.includes()` is also case sensitive when using strings

```JavaScript
const bookshelf = ["Moby dick", "Little Women", "The Great Gatsby", "Pride and Prejudice"];

if (bookshelf.includes("Moby dick")) {
    console.log(`We found the correct book.`); // We found the correct book.
} else {
    console.log(`We could not find the correct book.`);
}
```

## Sort
* The `array.sort()` method sorts an array of strings alphabetically
* This method only works for strings and not numbers, it receives them as their character values instead. This can be resoled by providing a comparison function
* The sort method mutates the original array
```JavaScript
const names = ["Anne", "Carl", "Bob", "Dean"];

names.sort();
console.log(names); // ['Anne', 'Bob', 'Carl', 'Dean']
```

```JavaScript
const numbers = [6, 3, 1, 7, 9, 2, 15, 25, 99];

// Ascending numbers.sort((a, b) => a - b);
// descending numbers.sort((a, b) => b -a);

console.log(numbers.sort((a, b) => a - b)); // [1, 2, 3, 6, 7, 9, 15, 25, 99]
```

## Some and Every

### Some
* The `array.some` method tests that at least one element in the array passes a function.
* If at least 1 element is passing the function test, it will return the Boolean value `true`
* `array.some` loops through an array, meaning the function doesn't need to be defined
```JavaScript
const array = [1, 2, 3, 4, 5]
console.log(array.some((number) => number > 3)); // true
```

### Every
* The `array.every` methods tests that every element in the array passes a function
* If at least 1 element fails the function test, it will return the Boolean value `false`
```JavaScript
const array = [1, 2, 3, 4, 5]
console.log(array.every((number) => number > 3)); // false
```

## Reduce
* `array.reduce()` starts with all the elements from an array, iterates over them and computes them to a single value
* The `array.reduce()` method takes 2 parameters: `accumulator` and `currentValue`
* Accumulator is something that we initialise, then the call-back function is executed many times
* In each time, the `currentValue` will be set to one element of the array
* In each call the current value is added to the accumulator
* The `array.reduce()` method takes two arguments, the first one is the call-back function that runs for each element in the array
* The second one is the initial value of the accumulator
* The result of the `reducer` method is always going to be a single value

#### forLoop example
```JavaScript
const groceryItems = [29, 12, 45, 35, 87, 110];
let total = 0;

groceryItems.forEach((item) => total += item);

console.log(total); // 318
```

#### reduce example
```JavaScript
const groceryItems = [29, 12, 45, 35, 87, 110];

const total = groceryItems.reduce((accumulator, currentValue) => {
    return accumulator + currentValue;

}, 0);

console.log(total); // 318
```

#### Calculating the sum of numbers in an array
```JavaScript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const sum = numbers.reduce((acc, val) => {
    return acc + val;
}, 0);

// acc = 0, val = 1 => 0 + 1 === 1
// acc = 1, val = 2 => 1 + 2 === 3
// acc = 3, val = 3 => 3 + 3 === 6
// acc = 6, val = 4 => 6 + 4 === 10
// acc = 10, val = 5 => 10 + 5 === 15

console.log(sum); // 55
```
* We start with an accumulator
* We loop through an array
* We convert all the elements to a single value, which in this case, a sum of all the values

#### Calculating the sum of numbers in an array - ES6
```JavaScript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const sum = numbers.reduce((acc, val) => acc + val)
console.log(sum); // 55
```
