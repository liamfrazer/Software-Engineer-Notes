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
* 

## Logical Operators
* 

## Assignment Operators
* 

