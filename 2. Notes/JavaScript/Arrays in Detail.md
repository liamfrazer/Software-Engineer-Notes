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


## ForEach

## Map

## Filter

## Find

## Includes

## Sort

## Some and Every

## Reduce