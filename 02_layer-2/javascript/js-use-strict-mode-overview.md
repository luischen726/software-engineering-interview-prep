# JavaScript: Strict Mode Overview [check] 🟡

## Picture

[Your mental picture]

## Flow
```
-> strict mode enabled
-> assignment to undeclared variable
-> ReferenceError
```
## 10-second answer

`use strict` is a directive that indicate script should be execute under strict mode. it prevents silently accepting certain programming mistake that cause bugs later.  

## 60-second answer

The `use strict` is a directive that switch entire script or function body into strict mode.  

It changes how JavaScript interprets and executes certain operations that  prevents silently accepting certain programming mistake that cause bug later.

The `use strict` should be placed on top of entire script or function body to enable.  Modern Es module apply `use strict` automatically if file is execute under ES module. 

A common mistake is placing "use strict" after executable statements. In a traditional script, this prevents the directive from activating strict mode.

## Tiny example

- place one top of entire script or function body
    ```js
    //.js
    'use strict'
    ...

    ```
    ```js
    function helloword(){
        'use strict'
         console.log("Hello");
    }
    ```
- in ES module
    ```mjs
    //it includes 'use strict' automatically
    undeclaredPrice = 100; // ReferenceError
    ```

- benefit with strict mode
    - without strict mode
    ```js
    //accept by run time
    name = 100
    ```
    - with strict more
    ```js
    'use strict'
    undeclaredPrice  = 100 // ReferenceError
    ```
## Common mistake

- if 'use strict' is not on top of executable statement in tradition js, entire script stays in normal mode 
```js
hello = "wold"
'use strict'

console.log(hello)

```

## See also

[Links to related Layer-2 cards]