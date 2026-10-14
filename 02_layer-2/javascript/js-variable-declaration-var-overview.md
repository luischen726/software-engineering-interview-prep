# JavaScript: Variable declaration `var` Overview [check] 🟡

## Picture

[Your mental picture]

## Flow

declare a variable with `var`-> ignore `if` block statement as a scope boundary

## 10-second answer

`var` is a JavaScript keyword to declaring a variable which is function-scoped rather than block-scoped. we need to understand it for maintain old version Javascript code. Even it usually be avoided due to `const`and `let`.

## 60-second answer


`var` is a JavaScript keyword to declaring a variable. the different with `let` is that it is not limited by block scope such as `if` but it is limited by functions block scope. 

the feature be introduce at early stage of Javascript. we need to understand it for maintain old version Javascript code. Even it usually be avoided due to `const`and `let`.  

`var` can be place before identifier to declare a variable. 

A common mistake is that it returns `undefine` instead of `ReferenceError` when there is declaration of `var` be placed after execute statement. Because JavaScript processes the var declaration when preparing the scope for execution.The variable is initialized to `undefined` before the statements execute.

## Tiny example

### how hoisting and function scope work together.

```js
function calculatePrice() {
    console.log(price); // undefined

    if (true) {
        var price = 100;
    }

    console.log(price); // 100
}

calculatePrice();
```
1. Before execution: JavaScript processes the var price declaration and initializes it to undefined in the function scope.
2. First console.log(): Prints undefined because the assignment hasn't executed yet.
3. Inside the if block: price = 100 assigns a new value to the variable.
4. Second console.log(): Prints 100 because var is function-scoped, not block-scoped.


```js 
// A mental model of how var hoisting behaves
function calculatePrice() {
    var price; // Initialized to undefined

    console.log(price); // undefined

    if (true) {
        price = 100;
    }

    console.log(price); // 100
}
```



### another major difference between `var` and `let`.

```js 

function updatePrice() {
    if (true) {
        var price = 200;
    }

    console.log(price); // 200
}

```
```js 
function updatePrice() {
    if (true) {
        let price = 200;
    }

    console.log(price); // ReferenceError
}
```

- price is block-scoped. This is an important reason developers generally prefer `let` and `const`.

## Common mistake
### `var` is function-scoped
```js 
function calculate() {
    if (true) {
        var price = 100;
    }

    console.log(price); // 100
}

calculate();

console.log(price); // ReferenceError
```
- `var` is not limited by the if block.
- However, it is limited by the **function's scope**.


## See also
- [Variable overview](js-variable-overview.md) - declaration, assign, access

