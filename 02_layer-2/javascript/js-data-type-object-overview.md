# JavaScript: Data types `object` Overview [check] 🟡

## Picture


## Flow
```
Create object with key-value pairs
-> access property using dot or bracket notation
-> retrieve property value
```
## 10-second answer

object is non-primitive data that contains keyed collections of various data and complex entities. 

## 60-second answer
Object is one of eight data type in Js and it is not primitive.  

Object contains keyed collections of various data and complex entities that can be treat as one single collection value and it is much more organized. 

Object can be create by curly braces with optional list of properties. key need to be a strings or symbols and value could be anything. value can be access by key string name or dot notation. 

A common mistake is that uses array-index keys without understanding that Javascript enumerates array-index key into ascending numeric order. Program could provide result that out of expectation of developer. 

## Tiny example

### Create empty object syntax
```js
let user1 = new Object(); // Object constructor

let user2 = {}; // Object literal

```

### `computed properties`
```js
let fruit = prompt("Which fruit to buy?", "apple");
let bag = {};

// take property name from the fruit variable
bag[fruit] = 5;
```


## Common mistake
### ordered like an object(`for let key in object`) 
- issues: Using array-index keys when developer expect the insertion order

    ```js 
    let codes = {
    "49": "Germany",
    "41": "Switzerland",
    "44": "Great Britain",
    // ..,
    "1": "USA"
    };

    for (let code in codes) {
    alert(code); // 1, 41, 44, 49
    }
    ```
- `Integer properties` means that a string that can be converted to-and-from an integer without a change.   Javascript enumerates ascending numeric order if using array-index keys
    ```js
    // Number(...) explicitly converts to a number
    // Math.trunc is a built-in function that removes the decimal part
    alert( String(Math.trunc(Number("49"))) ); // "49", same, integer property
    alert( String(Math.trunc(Number("+49"))) ); // "49", not same "+49" ⇒ not integer property
    alert( String(Math.trunc(Number("1.2"))) ); // "1", not same "1.2" ⇒ not integer property
    ```
- solution: Making the key name non-integer. 
    ```js
    let codes = {
    "+49": "Germany",
    "+41": "Switzerland",
    "+44": "Great Britain",
    // ..,
    "+1": "USA"
    };

    for (let code in codes) {
    alert( +code ); // 49, 41, 44, 1
    }
    ```
## See also
- [JS: data types](js-data-types-overview.md) - object is one of eight types.
- [JS: variable](js-variable-overview.md) - Object is a value can be declare as variable
