# Stages of the object resistance to change
## Object.preventExtensions : prohibits adding new properties
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/preventExtensions
```javascript
var obj = {
    a: 5
};
Object.preventExtensions(obj);
obj.b = 'new property added';
console.log(obj.b);
```
| Non-strict mode  | Strict Mode |
| ------------- | ------------- |
| obj.b = undefined  | TypeError: Can't add property b, object is not extensible  |

## Object.seal : prohibits adding new properties AND modifying existing properties descriptions
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/seal
```javascript
var obj = {
    a: 5
};
Object.seal(obj); // Object.preventExtensions(obj) + sets configurable=false for all own properties
Object.defineProperty(obj, 'a', {
    enumerable : false
});
```
TypeError: Cannot redefine property: a

## Object.freeze : prohibits adding new props, modifying existing props descriptions and values
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze
```javascript
var obj = {
    a: 5
};
Object.freeze(obj);
obj.a = 6;
console.log(obj.a);
```
| Non-strict mode  | Strict Mode |
| ------------- | ------------- |
| obj.a=5  | TypeError: Cannot assign to read only property 'a' of #Object  |
