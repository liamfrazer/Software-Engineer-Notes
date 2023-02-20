Date: 2023-02-19
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Reference: [JavaScript Mastery Pro][https://javascript-mastery.teachable.com/courses/849847/]
Tags: #Arrays #Methods #ForEach #Map #Filter #Find #Includes #Sort #Some #Every #Reduce

---
# Arrays in Detail

## Arrays Intro
* We will often need an ordered collection, we use `arrays` to store ordered collections
* Array elements are numbered, starting with zero
* The datatype of an array is an object

### Declaration
```JavaScript
const months = ['January', 'February', 'March', 'April'];
```

* We can get an element by its number in square brackets
```JavaScript
const months = ['January', 'February', 'March', 'April'];
console.log(months[1]); // February
```

* We can replace an element
```JavaScript
const months = ['January', 'February', 'March', 'April'];
months[1] = 'Not February'

console.log(months); // ['January', 'Not February', 'March', 'April']
```

* We can add a new element to the array
```JavaScript
const months = ['January', 'February', 'March', 'April'];
months[4] = 'May';

console.log(months); // ['January', 'February', 'March', 'April', 'May']
```

* The total count of the elements in the array is its length
```JavaScript
const months = ['January', 'February', 'March', 'April'];
months[4] = 'May';

console.log(months.length); // 5
```

* An array can store elements of any type
```JavaScript
const testArray = [
    'Apple',
    { name: 'Liam' },
    true,
    function () {
        alert('Hello');
    }
];
```

* We will often require to loop through all the elements of an array
```JavaScript
const months = ['January', 'February', 'March', 'April'];

  for (let i = 0; i < months.length; i++) {
	 console.log(months[i]);
}
```
```console
January
February
March
April
```

## Methods
* Arrays contain a variety of premade functions which can manipulate the data
* Such as adding, removing, manipulating elements at certain positions

### `array.push(value)`
* The `array.push()` function adds a new elements, containing the entered variable, to the end of the array.
```JavaScript
const names = ["Liam", "Michael", "Frazer"];
console.log(names); // ['Liam', 'Michael', 'Frazer']

names.push("Dean");
console.log(names); // ['Liam', 'Michael', 'Frazer', 'Dean']
```
* `array.push()` returns the length of the array when the element is pushed
```JavaScript
const names = ["Liam", "Michael", "Frazer"];
const length = names.push("Dean")

console.log(names); // ['Liam', 'Michael', 'Frazer', 'Dean']
console.log(length); // 4
```

### `array.pop()`
* The `array.pop()` function will delete the last element of an array
* `array.pop()` does not return the final length of the array, but returns the value of the remove element.
* This can be great for transferring data between two arrays
* This can also be used to give the value one final use before popping it into the void
```JavaScript
const names = ["Liam", "Michael", "Frazer"];
const removedValue = names.pop()

console.log(names); // ['Liam', 'Michael']
console.log(removedValue); // Frazer
```

### `array.shift()`
* Shift works almost like pop, but deletes the first value in an array and moves the rest backwards
* `array.shift()` will also return the 'popped' value
```JavaScript
const names = ["Liam", "Michael", "Frazer"];
const removedValue = names.shift()

console.log(names); // ['Michael','Frazer']
console.log(removedValue); // Liam
```

### `array.unshift(value)`
* `array.unshift` adds a new value at the start of an array, instead of the end
* Much like `push`, it returns the new array length
```JavaScript
const names = ["Liam", "Michael", "Frazer"];
const length = names.unshift('Mr')

console.log(names); // ['Mr', 'Liam', 'Michael', 'Frazer']
console.log(length); // 4
```

### `array.splice()`
* The splice method allows you to `splice` values into the array.
* The first parameter determines where the new element or elements are placed
* The second parameter demines how many after that point should be deleted before placement
* Each subsequent condition is merely an element you wish to add
* This will also return an array of any deleted items, like `pop`
```JavaScript
const names = ["Liam", "Michael", "Frazer"];
names.splice(2, 0, "Mr", "test");

console.log(names); // ['Liam', 'Michael', 'Mr', 'test', 'Frazer']
```
```JavaScript
const names = ["Liam", "Michael", "Frazer"];
const removedValues = names.splice(0, 1)

console.log(names); // ['Michael', 'Frazer']
console.log(removedValues); // ['Liam']
```

### `array.slice()`
* Slice can make a new variable that contains every element from a certain point on in whatever array you feed it
* This does not remove it from the array
```JavaScript
const names = ["Liam", "Michael", "Frazer"];
const removedValues = names.slice(2)

console.log(names); // ['Liam', 'Michael', 'Frazer']
console.log(removedValues); // ['Frazer']
```


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
array.forEach((value, inidex) => {
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
* This `callback function` can have three arguments.
* The first argument is the value of the current element the loop is on
* The second argument is the index of the current value

### Using a named function as a Callback
```JavaScript
let names = ['Liam', 'Michael', 'Frazer'];

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




## Map

## Filter

## Find

## Includes

## Sort

## Some and Every

## Reduce