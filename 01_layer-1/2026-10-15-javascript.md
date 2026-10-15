# 2026-10-15

## Resource
- Material: [JavaScript.info](https://javascript.info/)
- Topic: [Data type](https://javascript.info/types)

## Fleeting note
- there are eight type of data in JS
  - Number represent integer and float. 
  - BigInt is use for number greater than `9007199254740991`
  - string = there are three type of quotes such as "", '', ``. "" and '' are simple quotes and backticks are "extended functionality" quote
  - Boolean = there are two value (`true` and `false`)
  - null value = it represents "nothing", "empty" or "value unknown" than other language represent
  - undefined = it represent that value is not assigned
  - object = it is used to store collections of data and more complex entities.
  - symbol = it is used to create unique identifiers for objects 
- dynamically typed means a Variable can store a data with any type and it also can be replace by other type of data
- variable other than object are called primitive that other value can contain only a single value
- `typeof` operator returns the type of the operand.
## Literature note
- Javascript data have eight types. there are number,bigint, string, boolean, null, undefined, object, and symbol types. all the type except for object are primitive. Javascript provides different types of a value affects which operations are available and how those operations behave. a variable can store one type of data and it can be replaced by other type during program execution. there is operator called `typeof` that can be use to find out what type that variable contain. A common mistake that use integer to contain a number greater than   9007199254740991 because not all digits fit into the fixed 64-bit storage. so bigint will be better choice for this issues.
## Example


## what should i promote?
- [js-data-types-overview](02_layer-2/javascript/js-data-types-overview.md)