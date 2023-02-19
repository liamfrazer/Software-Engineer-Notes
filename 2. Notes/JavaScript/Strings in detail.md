Date: 2023-02-18
MOC: [JavaScript](../../1.%20MOC/JavaScript.md)
Reference: [JavaScript Mastery Pro][https://javascript-mastery.teachable.com/courses/849847/]
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
console.log(`${2 + 2}`); // 4
```

* This also means we can make function calls inside of backtick strings
```JavaScript
const sum = (a, b) => a + b;
console.log(`The sum is ${sum(2, 2)}.`); // The sum is 4.
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
console.log(name.length); // 4
```

### First letter of a string
```JavaScript
const name = 'Liam'
console.log(name[0]); // L
```

### Last letter of a string
```JavaScript
const name = 'Liam'
console.log(name[name.length - 1]); // M
```

* Name of 3 is the last letter, because we always start from 0 and not 1
```JavaScript
const name = 'Liam'
console.log(name[4]); // undefined
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

### `str.slice()`
* The best method of getting a substring of a string is `str.slice()`
* `str.slice(start [, end]` will return the part of the string from `start`, to but not including `end`
```JavaScript
const exampleString = "JavaScript is a great language to learn";
console.log(exampleString.slice(0, 10)); // JavaScript
```

## Split a String

### `str.split()`
* Sometimes, we may want to split the string into multiple substrings
* To do this, we would be using the string method `str.split()`
* Below, we can split a sentence into words:
```JavaScript
const exampleString = "JavaScript is a great language to learn";
console.log(exampleString.split(' '));
```
```console
1.  (7) ['JavaScript', 'is', 'a', 'great', 'language', 'to', 'learn']

1.  0: "JavaScript"
2.  1: "is"
3.  2: "a"
4.  3: "great"
5.  4: "language"
6.  5: "to"
7.  6: "learn"
8.  length: 7
9.  [[Prototype]]: Array(0)
```

## Reverse, Repeat and Trim a String

### Reverse
* Reverse is not a built in string method, but once a string is split, this create an array, which we can reverse
* In the process below we:
	1. Split a string 
	2. Reverse the newly create array 
	3. Turn the array back into a string using `join()`
```JavaScript
const exampleString = "JavaScript";
const reverseString = exampleString.split('').reverse().join('');
console.log(reverseString); // tpircSavaJ
```

* Creating a reverse function
```JavaScript
const reverse = (string) => {
    reverseString = string.split('').reverse().join('');
    return reverseString;
}

string = reverse("Test");

console.log(string); // tseT
```


### Repeat
* The `str.repeat()` method can be used to repeat a string an `X` number of times
```JavaScript
const exampleString = "JavaScript";
const repeatString = exampleString.repeat(5);
console.log(repeatString); // JavaScriptJavaScriptJavaScriptJavaScriptJavaScript
```

### Trim
* The `str.trim()` method can be useful to clean up user input
* In the example below, we can trim the empty spaces around the input
```JavaScript
const exampleString = "              JavaScript               ";
const trimmedString = exampleString.trim();
console.log(trimmedString); // JavaScript
```


## String Exercise

```JavaScript
const guestList = 'Our guests are: Emma, Jacob, Isabella, Ethan';
```
1. Get a length of the string.
2. Store it in a variable called `length`
```JavaScript
const guestList = 'Our guests are: Emma, Jacob, Isabella, Ethan';

length = guestList.length
console.log(length); // 44
```
3. Uppercase the entire string.
4. Store the result in a variable called `uppercasedGuestList`
```JavaScript
const guestList = 'Our guests are: Emma, Jacob, Isabella, Ethan';

length = guestList.length
uppercasedGuestList = guestList.toUpperCase();

console.log(length); // 44
console.log(uppercasedGuestList); // OUR GUESTS ARE: EMMA, JACOB, ISABELLA, ETHAN
```
5. Check whether `ETHAN` is on the `upperCasedGuestList`
6. Store the answer in a variable called `isEthanOnTheList`
```JavaScript
const guestList = 'Our guests are: Emma, Jacob, Isabella, Ethan';

length = guestList.length
uppercasedGuestList = guestList.toUpperCase();
isEthanOnTheList = uppercasedGuestList.includes('ETHAN');

console.log(length); // 44
console.log(uppercasedGuestList); // OUR GUESTS ARE: EMMA, JACOB, ISABELLA, ETHAN
console.log(isEthanOnTheList); // true
```
7. Create a substring that only contains the following: `EMMA, JACOB, ISABELLA, ETHAN`
8. Store the answer in a variable called `substringGuests`
```JavaScript
const guestList = 'Our guests are: Emma, Jacob, Isabella, Ethan';

length = guestList.length
uppercasedGuestList = guestList.toUpperCase();
isEthanOnTheList = uppercasedGuestList.includes('ETHAN');
subStringSlice = uppercasedGuestList.indexOf(':') + 2;
subStringGuests = uppercasedGuestList.slice(subStringSlice);

console.log(length); // 44
console.log(uppercasedGuestList); // OUR GUESTS ARE: EMMA, JACOB, ISABELLA, ETHAN
console.log(isEthanOnTheList); // true
console.log(subStringSlice); // 16
console.log(subStringGuests); // EMMA, JACOB, ISABELLA, ETHAN
```
9. Out of the substring you just created, create an array of names of people that are on the list.
10. Store that array in a variable called `guests`
```JavaScript
const guestList = 'Our guests are: Emma, Jacob, Isabella, Ethan';
const length = guestList.length
const uppercasedGuestList = guestList.toUpperCase();
const isEthanOnTheList = uppercasedGuestList.includes('ETHAN');
const subStringSlice = uppercasedGuestList.indexOf(':') + 2;
const subStringGuests = uppercasedGuestList.slice(subStringSlice);
const guests = subStringGuests.split(', ');

console.log(length); // 44
console.log(uppercasedGuestList); // OUR GUESTS ARE: EMMA, JACOB, ISABELLA, ETHAN
console.log(isEthanOnTheList); // true
console.log(subStringSlice); // 16
console.log(subStringGuests); // EMMA, JACOB, ISABELLA, ETHAN
console.log(guests); // (4) ['EMMA', 'JACOB', 'ISABELLA', 'ETHAN']
```

