# React

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
- default keyword: what you import is always default
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
```
