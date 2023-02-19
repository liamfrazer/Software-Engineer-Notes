Date: 2023-02-19
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Reference: [JavaScript Mastery Pro][https://javascript-mastery.teachable.com/courses/849847/]
Tags: #Arrays #Methods #ForEach #Map #Filter #Find #Includes #Sort #Some #Every #Reduce

---
# Arrays in Detail

## Arrays Intro
* We will often need an ordered collection, we use `arrays` to store ordered collections
* Array elements are numbered, starting with zero

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

## ForEach

## Map

## Filter

## Find

## Includes

## Sort

## Some and Every

## Reduce