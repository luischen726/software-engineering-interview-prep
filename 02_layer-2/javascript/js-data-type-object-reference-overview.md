# JavaScript: Data types `object` reference Overview [check] 🟡

## Picture


## Flow

Declaring variable with object type -> Copy it to another variable -> modified object's property from origin variable -> Affecting all variable which holds that reference

## 10-second answer

A reference is address in memory to be stored in variable as object type. A reference can be copy and assign to multiple variable but it does not create a new object.

## 60-second answer
The difference between object and primitive is that A variable stores a object's address in memory such as "a reference". 

A reference can be copy and assign to multiple variable but it does not create a new object.

Modifying an object's property through one variable affects the same object accessed through other variables holding the same reference. When a Object is being assign to two variable that Both are linked to same address. So Changing object from variable-a that also affect variable-B. Assigning a primitive value to another variable copies the value itself, while assigning an object copies its reference. 

A command mistake is that copy directly a object variable to another variable that intents to use separately. Either object change own property another will also change.

## Tiny example



### Comparison by reference
- two variable references same object
    ```js
    let a = {};
    let b = a; // copy the reference

    alert( a == b ); // true, both variables reference the same object
    alert( a === b ); // true
    ```
- two variable references different object
    ```js
    let a = {};
    let b = {}; // two independent objects

    alert( a == b ); // false
### `Const` objects can be modified
    ```js
    const user = {
    name: "John"
    };

    user.name = "Pete"; // (*)

    alert(user.name); // Pete 
    ```
    - `(*)`: there is no error occur due to address does not be changes in object. 
    - Error only occurs when reassigning whole value in `user`  

## Common mistake
### object is only copied with reference
```js
let user = { name: 'John' };

let admin = user;

admin.name = 'Pete'; // changed by the "admin" reference

alert(user.name); // 'Pete', changes are seen from the "user" reference
```
## See also
- [JS: data types overview](js-data-types-overview.md) - object is one of eight types
- [JS: Object overview](js-data-type-object-overview.md) - Object type features.
- [JS: Variable](js-variable-overview.md) - object reference can be store in variable.  