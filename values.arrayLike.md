#Array-Like values
```javascript
var ps = document.getElementsByTagName('p');
console.log(typeof ps); // object
console.log(Object.getOwnPropertyNames(ps)); // ['0','1']
var psArray = Array.prototype.slice.call( ps );
console.log(psArray instanceof Array); // true!

(function f(){
    console.log(typeof arguments); // object 
    console.log(Object.getOwnPropertyNames(arguments)); //['0', '1', '2', '3', length, callee]
    var argArray = Array.prototype.slice.call(arguments);
    console.log(argArray instanceof Array); // true!
})(1,2,3,4);
```
