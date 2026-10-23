# 2026-10-22

## Resource
- Material: 
  - [JavaScript.info](https://javascript.info/)

- Topic: 
  - [Object](https://javascript.info/object)

## Fleeting note
- One of the fundamental differences versus primitives is that object are stored and copied "by reference".
-  A variable assigned to an object stores not the object itself, but its "address in memory" in other words "a reference".
-  When an object variable is copied, the reference is copied, but the object itself is not duplicated.
- In comparison for object, object compare another object that it actually compare reference rather than value. 
- object that declares by `const` property can be reassign because object only store reference for value.
- There is two way to clone object
  - `Object.assign`
  - Creating new object and replicate the structure of the existing object, by iterating over its properties and copying them on the primitive level.
- `object.assign` can not clone a property that is object nested in another object. 
- `structuredClone(object)` solve the problem of nested object cloning. 
- `structuredClone(object)` can clone most data types, such as objects, arrays, primitive values.
- `structuredClone(object)` fails when object property is functions. It requires more advance solution such as custom code or JavaScript library such as `lodash` 
## Literature note
- The difference between object and primitive is that A variable stores a object's address in memory such as "a reference". A reference can be copy and assign to multiple variable but it does not create a new object. Using reference to modified object property could be affected to all variable holds same reference. When a Object is being assign to two variable that Both are linked to same address. So Changing object from variable-a that also affect variable-B. Assigning a primitive value to another variable copies the value itself, while assigning an object copies its reference. A command mistake is that copy directly a object variable to another variable that intents to use separately. Either object change own property another will also change.
- `Object.assign()` is JavaScript method that copy from exist object into target object. When we need to create a separate object instead of sharing same reference. first parameter is placed with target object. Following object property will be copied into first parameter object in primitive level and object reference. A common mistake is that uses method to copy a object property that is also object. Both object holds same reference of nested object.  
- `structuredClone(object)` is JavaScript global function that implements deep cloning. It provide more complete copy function than `object.assign` which it is able to clone most data types, such as objects, arrays, primitive values. Use the function with the source value you want to clone. A common mistake that copy a object which property is function. You can use custom cloning logic when needed, but you should decide how functions should be handled rather than assuming they can be deep-cloned like ordinary objects.

### object is only copied with reference
```js
let user = { name: 'John' };

let admin = user;

admin.name = 'Pete'; // changed by the "admin" reference

alert(user.name); // 'Pete', changes are seen from the "user" reference
```
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
    ```

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
### `Object.assign`
- basic way to use 
    ```js
    let user = { name: "John" };

    let permissions1 = { canView: true };
    let permissions2 = { canEdit: true };

    // copies all properties from permissions1 and permissions2 into user
    Object.assign(user, permissions1, permissions2);

    // now user = { name: "John", canView: true, canEdit: true }
    alert(user.name); // John
    alert(user.canView); // true
    alert(user.canEdit); // true
    ```
- it overwritten property already exist
    ```js
    let user = { name: "John" };

    Object.assign(user, { name: "Pete" });

    alert(user.name); // now user = { name: "Pete" }
    ```
- simple clone
    ```js
    let user = {
    name: "John",
    age: 30
    };

    let clone = Object.assign({}, user);

    alert(clone.name); // John
    alert(clone.age); // 30
    ```


## what should i promote?
- [js-data-type-object-reference-overview]()
- [js-data-type-object-assign]()
- [js-global-function-structuredClone]()