 > a type is an intrinsic, built-in set of characteristics that uniquely identifies 
 the behavior of a particular value and distinguishes it from other values, 
 both to the engine and to the developer.
 
# Built-in types
```javascript
console.log(typeof undefined); // 'undefined'
console.log(typeof null); // 'object' but should be null!!
console.log(typeof 'abc'); // 'string'
console.log(typeof 13); // 'number'
console.log(typeof true); // 'boolean'
console.log(typeof {}); // 'object'

var n = null;
console.log(!n && typeof n === 'object'); // true because null is the only 'falsy' object 

console.log(typeof function f(){}); // 'function' sub-type of object, "callable" object
```
