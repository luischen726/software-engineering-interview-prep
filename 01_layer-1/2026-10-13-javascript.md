# 2026-10-13

## Resource
- Material: [JavaScript.info](https://javascript.info/)
- Topic: ["use strict"](https://javascript.info/strict-mode)

## Fleeting note
- what is `use strict`
- The `use strict` enable and it can not be cancel in run time 
- Strict mode applies to entire scripts or to individual functions.
- does use string will be enable in modern js ?
- use strict mode prevents JavaScript from silently accepting certain programming mistakes that could cause bugs later.


## Literature note

- The `use strict` is a directive that switch entire script or function body into strict mode.  It changes how JavaScript interprets and executes certain operations that  prevents silently accepting certain programming mistake that cause bug later. the `use strict` should be placed on top of entire script or function body to enable.  Modern Es module apply `use strict` automatically if file is execute under ES module. the `use strict should be always on top. otherwise entire code will be under normal mode still. 

- how do i know file execute under ES module
  - file end with `.mjs`
  - in `package.json`
    ```json
    //Then your .js files are treated as ES Modules by default within that package.
    {
        "type": "module"
    }
    ```


what should i promote?
- [js-use-strict-mode-overview.md](../02_layer-2/javascript/js-use-strict-mode-overview.md)
