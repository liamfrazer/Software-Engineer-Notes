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

### String Length
```JavaScript
const name = 'Liam'
console.log(name.length);
```
```console
4
```
### First letter of a string
```JavaScript
const name = 'Liam'
console.log(name[0]);
```
```console
L
```
### Last letter of a string
```JavaScript
const name = 'Liam'
console.log(name[name.length - 1]);
```
```console
M
```
* Name of 3 is the last letter, because we always start from 0 and not 1
```JavaScript
const name = 'Liam'
console.log(name[4]);
```
```console
undefined
```

## Change String Case
* In JavaScript, there are only two simple methods for changing the character case
* `string.toLowerCase()`
* `string.toUpperCase()`
```JavaScript
const mixedCaseString = "Hello! How are you, Liam?";

console.log(mixedCaseString.toLowerCase());
console.log(mixedCaseString.toUpperCase());
```
```console
hello! how are you, liam?
HELLO! HOW ARE YOU, LIAM?
```
### Property vs Method
```JavaScript
const mixedCaseString = "Hello! How are you, Liam?";

console.log(mixedCaseString.length); // This is a property with a dot notation without calling it

console.log(mixedCaseString.toUpperCase()); // This is called a method, as we're calling a method on a string constructor
```

## Searching for a Substring
* There are multiple ways to look for a substring within a string

### `str.indexOf()`
* The first method is `str.indexOf(substr, pos)`
* It looks for the `substr` in `str`, starting from the given position `pos`
* This returns the position where the match was found or `-1` if nothing can be found
```JavaScript
const exampleString = "JavaScript is a great language to learn";

console.log(exampleString.indexOf('great'));
console.log(exampleString.indexOf('Great'));
```
```console
16
-1
```
* The optional second parameter allows us to search starting from the given position.
* For instance, the first occurrence of `great` is at position 16
* To look for a second occurrence, we can start the search from position 17
```JavaScript
const exampleString = "JavaScript is a great language to learn";
console.log(exampleString.indexOf('great', 17)); // -1
```
```JavaScript
const exampleString = "JavaScript is a great language to learn, it has been a great language";

console.log(exampleString.indexOf('great', 17)); // -55
```

### `str.lastIndexOf()`
* `str.lastIndexOf(substr, position)`
* This method searches from the end of a string to its beginning
```JavaScript
const exampleString = "JavaScript is a great language to learn";
console.log(exampleString.lastIndexOf('great')); // 16
```

### `includes()`
* If I want to know whether a string includes something, but not interested in the position I can use `string.includes()`
* This returns the Boolean value of true or false
* This is the correct choice if we need to test for a match, but not the position
```JavaScript
const exampleString = "JavaScript is a great language to learn";
console.log(exampleString.includes('great')); //true
```
```JavaScript
const exampleString = "JavaScript is a great language to learn";
console.log(exampleString.includes('bad')); // false
```

### `str.startsWith()` and `str.endsWith()`
* Methods `str.startsWith` and `str.endsWith` do exactly as they say
```JavaScript
const exampleString = "JavaScript is a great language to learn";
console.log(exampleString.startsWith('J')); // true
console.log(exampleString.endsWith('.')); // false
```

## Getting a Substring

## Split a String

## Reverse, Repeat and Trim a String

