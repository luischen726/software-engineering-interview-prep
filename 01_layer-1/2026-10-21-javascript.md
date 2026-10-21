# 2026-10-21

## Resource
- Material: 
  - [JavaScript.info](https://javascript.info/)

- Topic: 
  - [Object](https://javascript.info/object)

## Fleeting note
- object is one of eight data type in Js.
- Object is not primitive
- object store keyed collections of various data and more complex entities. 
- object can be create with curly braces`{...}` with an optional list of properties. 
- A object property is `{key:value}`. `key` is a string (also called a "property name"), and `value` can be anything.
- object's property can be access by key's name in string for example `object["key"]`
- `computed properties` means that the property name should be taken from dynamic string
- `obj.__proto__` can not be reassign with non-object value
- `in` operator can be use to check if object have certain name of key. for example `"key" in object`
- Using `in` operator instead of `object.key === undefined` because certain situation like `{key:undefined}` that `obj.key === undefined` still will be `true`.
- ordered like an object(`for let key in object`) that key is sorted if key name is used with number only Such as `5,6,7,1, is sorted to 1,5,6,7`. it is better to avoid by naming key with non-integer only.
## Literature note
- Object is one of eight data type in Js and it is not primitive.  Object contains keyed collections of various data and complex entities that can be treat as one single collection value and it is much more organized. Object can be create by curly braces with optional list of properties. key need to be a strings or symbols and value could be anything. value can be access by key string name or dot notation. A common mistake is that uses array-index keys without understanding that Javascript enumerates array-index key into ascending numeric order. Program could provide result that out of expectation of developer.  

## Example
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

### `obj.__proto__`
```js
let obj = {};
obj.__proto__ = 5; // assign a number
alert(obj.__proto__); // [object Object] - the value is an object, didn't work as intended
```

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
## what should i promote?
- [js-data-type-object-overview.md]()