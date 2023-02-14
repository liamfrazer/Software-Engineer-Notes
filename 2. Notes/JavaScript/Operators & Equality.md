Date: 2023-02-14
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Tags: #operators #equality

---
# Operators & Equality

## Arithmetic Operators
* Arithmetic operators are used to perform mathematical operations between numeric operands
* Simple operators are;
	* `+`
	* `*`
	* `-`
	* `/`
```JavaScript
const a = 5;
const b = 10;
let result = 0;
// Addition

result = a + b;
console.log(result);
```

```JavaScript
const a = 5;
const b = 10;
let result;

// Addition
result = a + b;
console.log(result);

// Subtraction
result = a - b;
console.log(result);

// Multiplication
result = a * b;
console.log(result);

// Division
result = a / b;
console.log(result);

// Modulo Operator
result = a % b;
console.log(result);

// Increment
result++;
console.log(result);

// Decrement
result--;
console.log(result);

// Exponentiation
result = a ** b;
console.log(result);
```

* Exponent means A to the power of B (5 to the power of 10)
* Modulo is when you divide A by B, the modulo is the remainder
	* 13 / 12 = 1 (remainder 1)
	* 1 / 12 = 0 (1 fits 0 times into 12 and the remainder is 1)
	* 15 / 11 = 1 (remainder is 4)
	* 4 / 11 = 0 (remainder is 4)


## Comparison Operators and Equality
* Comparison operators compare two values and return a Boolean value, either true or false.
* The return value of a comparison operator is always going to return a Boolean value.
* Equality operators allow us to test when a value is equal, or whether a value is not equal
```JavaScript
const a = 5;
const b = 10;

// Is A greater than B
console.log(a > b);

// Is A greater or equal to B
console.log(a >= b);

// Is A less than B
console.log(a < b);

// Is A less than or equal to B
console.log(a <= b);

// Is A equal to B
console.log(a == b);

// Is A NOT equal to B
console.log(a != b);

// Is A STRICTLY equal to B
console.log(a === b);

// Is A STRICTLY NOT equal to B
console.log(a !== b);
```
* All comparison operators and equality operators will only return Boolean values (true or false)


## Strict vs Loose Equality

### Strict Equality using `===`
* Two values are equal when they are the same value
```JavaScript
console.log("String" === "String"); // true
console.log(2 === 2); // true
```

* JavaScript allows us to test loose equality.
* Things may be considered loosely equal even if they refer to different values that look similar
```JavaScript
console.log(5 == "5"); // true
```

* With the strict equality `===`, the JavaScript interpreter compares the values as well as their types.
* JavaScript will only return true when both the value and the type are the same.
```JavaScript
console.log(20 === "20"); // false
```
* As the first value is a number, and the second value is a string, JavaScript will return false as the two types are different

### Loose Equality
* Visual representation of strict versus loose equalities
	* https://dorey.github.io/JavaScript-Equality-Table/
* Loose equality does not compare the data types. This can introduce bugs and can be unpredictable.
* Swapping to strict equality will allow us to be more predictable with our code
```JavaScript
5 == "5" // true
```
* The number 5 should not equal the string "5", this is an example of where we should completely avoid loose equality and rely only on the strict equality.
```JavaScript
console.log(5 == "5"); // true
console.log(20 === "20"); // false

'' == '0' // false
0 == '' // true
0 == '0' // true

false == 'false' // false
false == '0' // true
false == undefined // false
false == null // false
null == undefined // true
```
![](../../3.%20Meta/Media/Pasted%20image%2020230214184931.png)
![](../../3.%20Meta/Media/Pasted%20image%2020230214185027.png)

## Logical Operators
* JavaScript includes three logical operators
	* `||` OR
	* `&&` AND
	* `!!` NOT

### And Operator `&&`
* `&&` checks whether ALL OPERANDS are truthy values.
* If they are truthy, this will return `true`, otherwise it will return `false`
```JavaScript
console.log(true && false); // false
console.log(true && true); // true
console.log(false && false); // false
console.log(true && true && false); // false
```

### OR Operator `||`
* || chests whether AT LEAST ONE OPERANDS is a true value.
* If there is at least one true, it will return `true`, otherwise it will return `false`
```JavaScript
console.log(true || false); // true
console.log(true || true); // true
console.log(false || false); // false
console.log(true || true || false); // true
```

### Not Operator `!`
* `!` is known as a NOT operator
* This will reverse the Boolean result of the condition
```JavaScript
console.log(!true); // false
console.log(!false); // true
```

## Assignment Operators
*  An assignment operator assigns a value to its left operands based on the value of its right operands
* The simplest form of an assignment operator is `=`
```JavaScript
const number = 5
```
* Assignment operators can be joined with one of the arithmetic operators
* The addition assignment can also be used with strings
```JavaScript
let number = 5;
let string = 'Hello';

number += 5; // number = number + 5;
number -= 5; // number = number - 5;
number *= 5; // number = number * 5;
number /= 5; // number = number / 5;
console.log(number); // 5

string += ', I am Liam';
console.log(string); // Hello, I am Liam
```



