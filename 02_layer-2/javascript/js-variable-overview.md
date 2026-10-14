# JavaScript: Variable Overview [check] 🟡

## Picture

[Your mental picture]

## Flow

Javascript keyword such as `const`, `let`, or `var` -> variable name(Identifier) -> assign value.

## 10-second answer

A variable is a named binding associated with a value that is accessible, reuseable and store data during program execution. 

## 60-second answer
A variable is a named binding associated with a value. 

It helps program to store the information that can be reused during program execution. 

Javascript use syntax such as `const`,`let` or `var` to declare a variable. The variable can be reuse when needed. 

A common mistake is that reassigns complete value  which declares by `const`

## Tiny example

### declaration
```js
var userName = "Luis";
let something;
const anotherThing = 100 // it can not be reassign and value needs to be provide
let user = 'John', age = 25, message = 'Hello'; // works but not recommend



console.log(userName) // print "Luis"
console.log(something) // print undefined

```
    - `var` = JavaScript declaration keyword
    - `userName` = Identifier
    - "luis" = assigned value 


### `const` declaration
```js 
const user = {
    name: "Luis"
};

user.name = "John"; // Allowed

user = {}; // TypeError
```

## Common mistake

### Reassigning `const` declaration
```js
const hello = "world"

hello = "new world" // Error occurs 
```
    - `const` prevents complete value to be reassign

## See also
- [`use strict` impact on how variable to be declare](js-use-strict-mode-overview.md)
[Links to related Layer-2 cards]