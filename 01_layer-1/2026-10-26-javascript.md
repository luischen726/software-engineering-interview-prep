# 2026-10-26

## Resource
- Material: 
  - [JavaScript.info](https://javascript.info/)

- Topic: 
  - [Object: Garbage collection](https://javascript.info/garbage-collection)

## Fleeting note
- Memory management In Javascript is performed invisible and automatically
- Every data types take memory
- what happen to values we do not need anymore? how Javascript remove value from memory?
- The main concept of memory management in JavaScript is **reachability**.
- The reachable value is data what can be accessed or used. that is in memory for sure. 
- There is a set of reachable values (root value) that can not be remove from memory
  - The currently executing function, its local variables and parameters.
  - Other functions on the current chain of nested calls, their local variables and parameters.
  - Global variables.
  - (there are some other, internal ones as well)
- Any other value is considered reachable if it’s reachable from a root by **a reference** or by **a chain of references**.
  - For instance, if there’s an object in a global variable, and that object has a property referencing another object, that object is considered reachable. And those that it references are also reachable. Detailed examples to follow.
- `garbage collector` is a background process in the JS engine that monitors all objects and removes those that have become unreachable. 
- When removing object, it needs to make sure all variable does not store a reference that object need to be remove
- A unreachable object that contains outgoing references  that is removed if it is unreachable.
- Unreachable island is that a object contains reference of objects that is not reachable. 
- The basic garbage collection algorithm is called **“mark-and-sweep”** .
- Garbage collection steps are regularly performed
  - Garbage colector starts from root of object and `marks` them. Then it visits all reference from marked object. then marks all reference  so it does not visits more than once. it progresses until all reference from root that are visited. then it removes all expect marked object.
- Garbage collections have some of the optimizations that makes it run faster and not introduce any delays into the code execution 
  - Generational collection
  - Incremental collection
  - Idle-time collections
- Garbage collection is an automatic memory management mechanism whose primary purpose is to reclaim memory occupied by objects that are no longer reachable.
- Garbage collection is part of memory management
- Memory management have three stages:
  - Memory allocation - Reserve memory to store data
  - Memory usage - Read or modify the stored data
  - Memory release - Reclaim memory that is no longer needed. garbage collection primary handle this stage.
- 
## Literature note
- Garbage collection is a automatic mechanism of memory management that reclaim memory occurred by unreachable object . the main concept is about "reachability" for finding object by a reference from roots to determined that object stay or go. garbage collector reaches a object by the reference then marks the object and keep go on from reference inside of object. A common mistake is that garbage collector does not decide to remove unreachable object. it is Javascript engine decide it


## Examples

### General process with a reference

```js
// 1. user has a reference to the object
let user = { // user store a reference of object with global variable
  name: "John" // primitive value that stores inside user object
};

// 2 . User is overwritten 
// {"name":"John"} is lost reference and it is not reachable now 
//Garbage collector will junk the data and free the memory.
user = null;

```
### Two references
```js 
// user has a reference to the object
let user = {
  name: "John"
};
//1. another variable stores a reference as user.
// a reference is stored in both admin and user
let admin = user;

// 2. remove a reference from user but admin still has it
// {"name":"John"} is still reachable. 
user = null;

// 3. object became unreachable and  garbage collector remove it.
admin = null;
```

### interlinked objects and Unreachable island
```js 
function marry(man, woman) {
  woman.husband = man;
  man.wife = woman;

  return { // create a object that interlinked to other object
    father: man,
    mother: woman
  }
}

let family = marry({ // creates island like chain
  name: "John"
}, {
  name: "Ann"
});

// break accessability for {name:john, wife: reference to Ann object} and it got removed 
// 
delete family.father;
delete family.mother.husband;

family = null; // unreachable island that object contains outgoing reference is removed

```


## what should i promote?
[js-data-type-object-garbage-collection-overview](02_layer-2/javascript/js-data-type-object-garbage-collection-overview.md)