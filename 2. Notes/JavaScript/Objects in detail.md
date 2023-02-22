Date: 2023-02-22
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Reference: https://javascript-mastery.teachable.com/courses/849847/
Tags: #Objects #Methods #Properties

---
# Objects in detail

## Objects Intro
* Objects are the most important data-type and building block for modern JavaScript
* Objects can store multiple values, which makes them different to primitive data-types which all store a single value
* In JavaScript an object is a standalone entity, with properties and type
* JavaScript objects can have properties, which define their characteristics
* In simple words, an object is an unordered collection of related data in the form of `key` and `value` pairs

```JavaScript
const person = {
    firstName: 'Liam',
    lastName: 'Frazer',
    age: 28,
}
```
* We created an object with the set of curly brackets and assign it to a variable
* Inside, we have `key` and `value` pairs
* The first key in the person object is `firstName`, with the corresponding value of `Liam`
* We also have the keys of `lastName` & `age`
* Each of these keys is referred to as `properties` of the object
* As we working with objects, we are not worried about the order, this is what we can use arrays for
* Values in an object can be of any type

```JavaScript
const person = {
    firstName: 'Liam',
    lastName: 'Frazer',
    age: 28,
    car: {
        year: 2017,
        colour: 'grey'
    }
}
```
* We can nest objects inside other objects
* We can also add variables as values in an object
* A variable is just a box that holds a value
```JavaScript
const firstName = 'Liam';

const person = {
    firstname: firstName
}

console.log(person); // {firstname: 'Liam'}
```
* One thing we can notice is that the `key` and `value` have the same name.
* If that is the case, JavaScript allows the following to happen
```JavaScript
const firstName = 'Liam';
const person = {
    firstName
}

console.log(person); // {firstname: 'Liam'}
```

## Accessing, Adding and Updating Properties of an Object

### Dot Notation
* Dot notation allows us to retrieve some values from an object
* If we want to get only the `firstName` of our person, we can do the following:
```JavaScript
person.firstName
```
* We can also add or overwrite some properties:
```JavaScript

```



## Built in Methods

## Methods
