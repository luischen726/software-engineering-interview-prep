# JavaScript: Data types Overview [check] 🟡

## Picture

[Your mental picture]

## Flow
```
Assign value
    ↓
JavaScript determines the value's type
    ↓
Operations behave according to the types involved
    ↓
Variable may be reassigned to another type (if reassignment is allowed)
```
## 10-second answer

Javascript data have eight types which affects which operations are available and how those operation behave. 

## 60-second answer

Javascript data have eight types. there are `number`,`bigint`, `string`, `boolean`, `null`, `undefined`, `object`, and `symbol` types. all the type except for object are primitive. 

Javascript provides different types of a value affects which operations are available and how those operations behave. 

a variable can store one type of data and it can be replaced by other type during program execution. there is operator called `typeof` that can be use to find out what type that variable contain. 

A common mistake that use integer to contain a number greater than   9007199254740991 because bigint supports integers of arbitrary precision, subject to available memory.

## Tiny example

### `number`

```js
let n = 123; //integer
n = 12.345; // float

console.log(1 / 0 ) //Infinity
console.log( "not a number" / 2 ) // NaN, such division is erroneous
```
### `bigint` 
```js 
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```

### `string` 
```js 

let str = "Hello"; // double quote
let str2 = 'Single quotes are ok too'; // single quote
let phrase = `can embed another ${str}`; // extend functionality quote

```


### `boolean` 

```js 

let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked

let isGreater = 4 > 1;

console.log( isGreater ); // true (the comparison result is "yes")

```
### `null` 

```js
let age = null; //represents “nothing”, “empty” or “value unknown” than other language.

```

### `undefined` 
```js 
let age;

alert(age); // shows "undefined"
```

### `object` 

```js 
let o = {
    hello: 100,
    world: null
}
```

### `symbol`

```js 

const id = Symbol("id");

console.log(typeof id); // "symbol"

```

### `typeof` operator
```js 
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object" (historical behaviour; null is primitive)

function greet() {
    return "Hello";
}

typeof greet // "function"  (3)
```

## Common mistake

### type coercion: string with `-` operator

```js
let price = "200";

console.log(price - 50); //150
console.log(typeof (price - 50));// number
```
- When JavaScript encounters `"200" - 50`, it automatically converts `"200"` into the number `200`.
## See also
- [Variable](js-variable-overview.md) - a variable store one type of value
