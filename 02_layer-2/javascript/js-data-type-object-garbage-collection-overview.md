# JavaScript: Data types `object`: garbage collections Overview [check] 🟡

## Picture


## Flow

```less
Garbage collection runs automatically
    ↓
Start from roots
    ↓
Follow references and mark reachable objects
    ↓
Identify unmarked (unreachable) objects
    ↓
Reclaim their memory
```

## 10-second answer

Garbage collection is a automatic mechanism of memory management that reclaim memory occurred by unreachable object.


## 60-second answer

Garbage collection is a automatic mechanism of memory management that reclaim memory occurred by unreachable object. 

The main concept is about "reachability" for finding object by a reference from roots to determined that object stay or go. 

Garbage collector reaches a object by the reference then marks the object and keep go on from reference inside of object. 

A common mistake is assuming that garbage collection happens immediately when an object becomes unreachable. After marking all reachable objects, the garbage collector can reclaim memory occupied by unmarked objects.
## Tiny example

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
### interlinked objects 

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

delete family.father;
delete family.mother.husband;

```

### Unreachable island
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


family = null; // unreachable island that object contains outgoing reference is removed

```



## Common mistake
- 

## See also
- [JS: object](js-data-type-object-overview.md) - object is the main focus from garbage collection 
- [JS: Reference of Object](js-data-type-object-reference-overview.md) - garbage collector reach object through reference  