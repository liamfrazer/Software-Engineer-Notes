Date: 2023-02-18
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Tags: #Strings #Length #Case #Search #SubString #Getting #Split #Reverse #Repeat #Trim

---
# Strings in detail

## Strings intro
* In JavaScript, we use strings to store text
* String is nothing more than a primitive data type
* Strings can be stored in three ways
```JavaScript
const single = 'This is a string written inside single quotes';
const double = "This is a string written inside double quotes";
const backticks = `This is a string written inside of backticks`;
```
* Strings created with a single and double quotes are the same
* Strings created with backticks provide extended functionality
* Backticks strings are dynamic, they allow us to execute JavaScript logic
```JavaScript
console.log(`${2 + 2}`);
```
```console
4
```
* This also means we can make function calls inside of backtick strings
```JavaScript
const sum = (a, b) => a + b;
console.log(`The sum is ${sum(2, 2)}.`);
```
```console
The sum is 4.
```
* Backtick strings can also be used across multiple lines.
* Single or double quote strings would create an error if we did this
```JavaScript
const numbers = `
	1
	2
	3
	4
`;
```

* Escape characters can be used to prevent additional single or double quotes from breaking strings, but this is not a great overall solution.
* Instead, using backtick strings would help prevent this issue from occurring.
```JavaScript
const brokenGreeting = 'Hi, I\'m Liam, \"Liam Frazer\".';
const fixedGreeting = `Hi, I'm Liam, "Liam Frazer".`;

console.log(brokenGreeting);
console.log(fixedGreeting);
```
```console
Hi, I'm Liam, "Liam Frazer".
Hi, I'm Liam, "Liam Frazer".
```


## String Length and Basic Properties

## Change String Case

## Searching for a Substring

## Getting a Substring

## Split a String

## Reverse, Repeat and Trim a String

