# JavaScript: Variable naming Overview [check] 🟡

## Picture

[Your mental picture]

## Flow
think a meaningful name -> make sure it follow principle 
## 10-second answer

Variable naming are rules that helps developer to name variable for readability and meaningful way. 

## 60-second answer
Variable naming are rules that helps developer to name variable for readability and meaningful way. 

It indicate purpose of the data in memory space. it helps developer to maintain ,reuse, and follow.  

There are several rules for naming a variable. First, first character can not be dight. Second, Variable name can be character, dight, and symbol such as `$` and `_`.  camelCase is recommend for readability. JavaScript reserved words such as class and return cannot be used as variable names.

A common mistake is that ignores the capital and lower case of variable name when reuse or reassign. 
## Tiny example

### `camelCase` and `Snake case`

```js
let helloWorld = "nice" // camelCase
let hello_new_world = "Jesus" // snake case
```
### Variable name can be character, dight, and symbol such as `$` and `_`

```js
let _hello = "world";
let $ = 100;
let _= 200;
let print100 = 100 

console.log($ + _ ) // print 300
console.log(print100) // print 100


```

## Common mistake

### First world can not be dight

```js
let 100_ = 100 // SyntaxError occur
```

## See also
- [Variable overview](js-variable-overview.md) - declaration, assign, access
- [list of reserved word ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#reserved_words) that can not use for naming variable
