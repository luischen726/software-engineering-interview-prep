# 2026-10-13

## Resource
- Material: [JavaScript.info](https://javascript.info/)
- Topic: [Variable](https://javascript.info/variables)

## Fleeting note
- variable is name of storage
- name associate with memory space
- syntax to declare a variable: `const`, `let`, and `var`
- the different between `var` and `let` is that `var` can be reassign from outside of `if` block scope but not function block scope
- When variable be reassign, it changes value that a variable holds
- variable's name can not be declare multiple times with `const` and `let`
- there are two rule for naming variable
  - name can be character, dight, or symbols such as `$`, and `_`.
  - first character should not be dights
- camelCase is recommend for variable naming
- Capital and lower case are matter for variable naming
- There is a [list of reserved word ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#reserved_words) that can not use for naming variable
- Non-Latin letters are allowed, but not recommended
- An assignment without `use strict` directive that it is allows without declaration syntax such as `const`, `let`, or `var`.
- `const` is good at declaring something without changing later
- `const` occurs error if user intent to changes value
- the name of variable is important for readability. 
## Literature note
- A variable is a named binding associated with a value. it helps program to store the information that can be reused during program execution. Javascript use syntax such as `const`,`let` or `var` to declare a variable. The variable can be reuse when needed. A common mistake is that reassigns complete value  which declares by `const`
  
- Variable naming are rules that helps developer to name variable for readability and meaningful way. It indicate purpose of the data in memory space. it helps developer to maintain ,reuse, and follow.  There are two principles to name a variable. First, first character can not be dight. Second, Variable name can be character, dight, and symbol such as `$` and `_`.  camelCase is recommend for readability. A common mistake is that ignores the capital and lower case of variable name when reuse or reassign. 

- `var` is a JavaScript keyword to  declaring a variable. the different with `let` is that it is not limited by block scope such as `if` but it is limited by functions block scope. the feature be introduce at early stage of Javascript. we need to understand it for maintain old version Javascript code. Even it usually be avoided due to `const`and `let`.  `var` can be place before identifier to declare a variable. A common mistake is that it returns `undefine` instead of `ReferenceError` when there is declaration of `var` be placed after execute statement. Because JavaScript processes the var declaration when preparing the scope for execution.The variable is initialized to `undefined` before the statements execute.
## Example


## what should i promote?
- [js-variable-overview](02_layer-2/javascript/js-variable-overview.md)
- [js-variable-naming-overview](02_layer-2/javascript/js-variable-naming-overview.md)
- [js-variable-declaration-var-overview](02_layer-2/javascript/js-variable-declaration-var-overview.md)
