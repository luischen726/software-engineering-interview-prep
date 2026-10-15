# 2026-10-13

## Resource
- Material: [JavaScript.info](https://javascript.info/)
- Topic: [Variable](https://javascript.info/variables)


## Literature note
- A variable is a named binding associated with a value. it helps program to store the information that can be reused during program execution. Javascript use syntax such as `const`,`let` or `var` to declare a variable. The variable can be reuse when needed. A common mistake is that reassigns complete value  which declares by `const`
  
- Variable naming are rules that helps developer to name variable for readability and meaningful way. It indicate purpose of the data in memory space. it helps developer to maintain ,reuse, and follow.  There are two principles to name a variable. First, first character can not be dight. Second, Variable name can be character, dight, and symbol such as `$` and `_`.  camelCase is recommend for readability. A common mistake is that ignores the capital and lower case of variable name when reuse or reassign. 

- `var` is a JavaScript keyword to  declaring a variable. the different with `let` is that it is not limited by block scope such as `if` but it is limited by functions block scope. the feature be introduce at early stage of Javascript. we need to understand it for maintain old version Javascript code. Even it usually be avoided due to `const`and `let`.  `var` can be place before identifier to declare a variable. A common mistake is that it returns `undefine` instead of `ReferenceError` when there is declaration of `var` be placed after execute statement. Because JavaScript processes the var declaration when preparing the scope for execution.The variable is initialized to `undefined` before the statements execute.
## Example


## what should i promote?
- [js-variable-overview](02_layer-2/javascript/js-variable-overview.md)
- [js-variable-naming-overview](02_layer-2/javascript/js-variable-naming-overview.md)
- [js-variable-declaration-var-overview](02_layer-2/javascript/js-variable-declaration-var-overview.md)
