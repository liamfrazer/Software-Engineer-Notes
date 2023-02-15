Date: 2023-02-14
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Tags: #logic #control #flow

---
# Logic & Control Flow

## If Statement
* `IF` statements consists of a condition that is evaluated to either `true` or `false`
* If the condition is evaluated to true, then the code inside of the block will run, else it will be skipped.
* An `else` statement does not have a condition, if nothing is matched, an `else` is executed.
* Simply if none of the other conditions evaluate to true, `else` is ran
```JavaScript
const age = 18;

if (age >= 18) {
    console.log("You may enter.");
} else if (age === 18) {
    console.log("You just turned 18");
} else {
    console.log("Please go away");
};
```

## Truthy & Falsy Values
* In JavaScript, we have truthy values and falsy values
* `true` & `false` values are not limited to `boolean` data types and comparisons in JavaScript, it can have many other forms.
* In JavaScript, a truthy value doesn't just mean the value is `true`, it means that the value coerces to true when evaluated in a Boolean context
* We don't need to explicitly check for `undefined` or `""`. Instead we can just check whether a value is truthy
```JavaScript
const dogs = 5;

if (dogs) {
    console.log(`You have ${dogs} dogs.`);
} else {
    console.log("You have no dogs.");
}
```
```JavaScript
You have 5 dogs.
```

### Falsy values
* false
* 0
* "",'',empty backticks
* null
* undefined
* NaN
```JavaScript
if (0) {
    console.log("In here");
} else {
    console.log("No, in here");
}
```

### Truthy values
* Everything that is not FALSY
```JavaScript
if (1) {
    console.log("In here");
} else {
    console.log("No, in here");
}
```
* https://sitepoint.com/javascript-thurthy-falsy/

## Truthy Falsy Logical Operators

### AND Operator
```JavaScript
console.log('truthy' && 1 && 999);
```
```JavaScript
999
```
* The && operator does the following:
	* It evaluates operands from left to right.
	* It converts them to a Boolean value.
	* If the result is `true`, it continues to the next value.
	* If the result is `false`, it stops and returns the original value of that operand
	* If all operands have been evaluated to true, it returns the last operands
* The above code returns 999 as all values were `truthy` and 999 is the last value on the list.

```JavaScript
console.log('truthy' && 0 && 999);
```
```JavaScript
0
```
* If one falsy value exists, it's going to stop and immediately return that value.
* If other words, AND returns the first falsy value or the last truthy value, if no falsy values have been found

### OR Operator
* The || operator does the following:
	* For each operand, it converts it to a boolean.
	* If the result is `true`, it stops and returns the original value of that operand
	* If all operands have been evaluated to falsy, it returns the last operand
* In other words, a chain of OR returns the first truthy value, or the last one if no truthy value is found.
```JavaScript
console.log('truthy' || 0 || 'test' || 999);
```
```JavaScript
truthy
```

```JavaScript
console.log('' || 0 || null || undefined);
```
```JavaScript
undefined
```
* If all the values were changed to falsy, it is going to return the last one

### Not Operator
* The ! operator accepts a single argument and does the following:
	* Converts the operand to boolean type: true/false
	* Returns the inverse value
```JavaScript
console.log(!true);
console.log(!false);
```
```JavaScript
false
true
```
* A double NOT `!!` is sometimes used for converting a value to Boolean type:
```JavaScript
console.log(!!"truthy");
console.log(!!null);
```
```JavaScript
true
false
```
* The first NOT converts the value to Boolean and returns the inverse
* The second NOT inverses it again.
* In the end, we have a plain value to Boolean conversion.

## Switch Statement
* The switch statement is very similar to the IF statement
* If you have a larger number of conditions, the switch statement might be more suitable
* The switch statement takes in a value, then checks it on a number of cases
```JavaScript
let superHero = 'Captain America';

switch (superHero) {
    case 'Iron Man':
        console.log('Iron Man');
        break;
    case 'Thor':
        console.log('Thor');
        break;
    case 'Captain America':
        console.log('Captain America');
        break;
    case 'Black Widow':
        console.log('Black Widow');
        break;
}
```
```JavaScript
Captain America
```
* In the example above, we passed the `superHero` variable to the switch statement
* The switch statement then executes the following check
```JavaScript
'Captain America' === 'Iron Man'
```
* As this is `false`, it skips past this case, then evaluates the next one
* As soon as it matches correctly, it will execute the code inside of that case
* The `break` keyword ends the switch when we get the correct case
* If we omit the break statement, the next case will be executed erven if the condition does not match the case
* If no cases match the correct value, switch statements include the `default` case
```JavaScript
let superHero = 'Hello';

switch (superHero) {
    case 'Iron Man':
        console.log('Iron Man');
        break;
    case 'Thor':
        console.log('Thor');
        break;
    case 'Captain America':
        console.log('Captain America');
        break;
    case 'Black Widow':
        console.log('Black Widow');
        break;
    default:
        console.log('Please enter a valid superhero name:');

}
```
```JavaScript
Please enter a valid superhero name:
```

## Ternary Operator
* The Ternary operator should be used for for the simple true or false checks
```pseudocode
condition ? value if true : value if false
```
* The equivalent `if` statement equivalent is as follows:
```psuedocode
if (condition) {
	value if true;
} else {
	value if false;
}
```

* IF statement
```JavaScript
const person = {
    age: 18,
}

if (person.age >= 18) {
    console.log('Legal age to drive');
} else {
    console.log('Not legal age to drive');
}
```
```JavaScript
Legal age to drive
```

* Ternary statement
```JavaScript
const person = {
    age: 18,
}

person.age >= 18 ? console.log('Legal age to drive') : console.log('Not legal age to drive');
```
```JavaScript
Legal age to drive
```

## Looping - While and For Loops

### For loop
* Instead of repeating ourselves, which breaks the DRY protocol, we can use the FOR loop instead
* A for loop will run `for` a specified number of times
* For loops are declared with three optional expressions separated by semicolons:
	* Initialization
	* condition
	* final expression
* These are then normally followed by a block statement
```psuedocode
for ([initalisation]; [condition]; [final-expression]){
	statement
}
```

* The initialisation statement is executed one time only before the loop starts
* This is typically used to define and setup the loop variable
* The condition statement is then evaluated at the beginning of every loop iteration
* This will continue as long as it evaluates to true
* Once the condition is false at the start of the iteration, the loop will stop executing

* If the condition starts with false, the loop will never execute
* The final-expression is executed at the end of each loop iteration
* This is prior to the next condition check
* This is usally used to increment or decrement the loop
```JavaScript
for (let i = 0; i <= 10; i++) {
    console.log(i);
}
```

### While loop
```JavaScript
let i = 0;
while (i <= 10) {
    console.log(i);
    i++;
}
```
* A single execution of the loop body is called an interation
* The code above will have 10 iterations
* Without i++, the loop would be infinite

