# Next Generation Javascript Feature

## 1. let and const
- var still works, let is new var
- let: variable values
- const: constant values

## 2. Arrow Functions
- Normal function:
``` javascript
function myFnc() {

}
```
- arrow function
```javascript 
const myFnc = () => {
}
```
- Special syntax for exactly one argument:
```javascript
// you can omit parentheses
const printMyName = name => {
    console.log(name);
}
```
- Special syntax for the function that only returns:
```javascript
// omit the return keyword and {}
const multiply = (number) => number*2;
```
## 3. Exports and Import (Modules)
- default keyword: what you import is always default (you can choose your name)
```javascript
// Person.js
const person = {
    name:'Max';
}

export default person

// app.js
import person from './person.js'
import prs from './person.js'
```
- Named keyword: import by their name, we need to give exact name.
```javascript
// Utility.js
export const claen = () => { ... }
export const baseData = () 10;

// app.js
import {baseData} from 'Utility.js'
import {clean} from 'Utility.js'

// An alternative
import * as bundled from 'Utility.js'
// bundled.clean, bundled.baseData
import {baseData as bd} bundled from 'Utility.js'
```

## 4. Classes
- Class:
```javascript
class Person {
    name='Max' // Property
    call = () => {...} // Method
}
```
- Usage:
```javascript
const myPerson = new Person()
myPerson.call();
console.log(myPerson.name)
```
- Constructor and inheritance
```javascript
class Human {
    contructor() {
        this.gender = 'male';
    }
    printGender() {
        console.log(this.gender);
    }
}
class Person extends Human {
    constructor () {
        super(); // You must call super method inorder to inherit
        this.name = 'Max';
        this.gender = 'female'
    }
    printMyName = () => {
        console.log(this.name);
    }
}
// ES6 Babel
class Human {
    gender = 'male';
    printGender() {
        console.log(this.gender);
    }
}
class Person extends Human {
        this.name = 'Max';
        this.gender = 'female'
    }
    printMyName = () => {
        console.log(this.name);
    }
}

```
- Properties: variables attached to classes/object
```javascript
// ES6
constructor () {
    this.myProperty = 'value';
}
// ES7
myProperty='value';
```
- Methods
```javascript
// ES6
myMethod() {...}
// ES7
myMethod=()=>{...}
```

##5. Spread & operator (...)
- Spread: Used to split up elements OR object properties.
```javascript
const newArray
```
- Rest: Used to merge a list of function arguments into an array.
```javascript
function sortArgs(...args) {
    return args.sort()
}

const numbers = [1, 2, 3];
const newNumbers = [numbers, 4] // [[1, 2, 3], 4]
const newNumbers = [...numbers, 4]; // [1, 2, 3, 4]

const person = {
    name='Max'
};

const newPerson = {
    ...person, // copy from person
    age: 28
}
//rest
const filter = (...args) => {
    return args.filter(el => el === 1);
    //=== check for type and value equality
}
filter(1, 2, 3); // [1]
```
## 6. Destructuring
Easily extract array elements or object properties and store them in variables.
```javascript
[a, ,b] = ["Hello", "World", "Max"]; // Array Destructuring
console.log(a); // Hello
console.log(b); // Max
{name} = {name:'Max', age: 28} // Object Destructuring
console.log(name); // Max
console.log(b); // age
```

## 7. Other important features
```javascript
// String, Numbers are Primitive type
const number = 1;
const num2 = number; //When restore, it will copy the value

// Array is reference type When restored, it will just be referenced
const number = [1, 2, 3];
const doubleNumArray = numbers.map((num) => {
    return num * 2
}) // map returns new array
```
