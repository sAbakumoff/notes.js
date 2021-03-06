#in operator - respects the prototype chain
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in
```javascript
var obj = {
    a: 5
};
var obj2 = Object.create(obj);
obj2.b = 77;
console.log('b in obj2', 'b' in obj2);//true
console.log('a in obj2', 'a' in obj2); //true through prototype chain
console.log('c in obj2', 'c' in obj2); // false
console.log('toString in obj2', 'toString' in obj2);//true through prototype chain
var array = [1,2,3,4];
console.log('0 in array', 0 in array); // true 
console.log('4 in array', 4 in array); // false as max index = 3 
```

#hasOwnProperty method - ignores prototype chain
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty
```javascript
var obj = {
    a: 5
};
var obj2 = Object.create(obj);
obj2.b = 77;
console.log('obj2 hasOwnProperty b', Object.prototype.hasOwnProperty.call(obj2, 'b'));//true
console.log('obj2 hasOwnProperty a', Object.prototype.hasOwnProperty.call(obj2, 'a')); //false
```
borrowing hasOwnProperty from prototype because of
```javascript
var obj = Object.create(null);
obj.a = 1;
console.log(obj.hasOwnProperty('a')); //TypeError: obj.hasOwnProperty is not a function
```
#Object.prototype.propertyIsEnumerable - ignores prototype chain
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/propertyIsEnumerable
```javascript
var o = {};
Object.defineProperty(o, 'p1', {enumerable : true});
Object.defineProperty(o, 'p2', {enumerable : false});
var o1 = Object.create(o);
Object.defineProperty(o1, 'p3', {enumerable : true});
Object.defineProperty(o1, 'p4', {enumerable : false});

console.log(o1.propertyIsEnumerable('p1')); //false
console.log(o1.propertyIsEnumerable('p2')); //false
console.log(o1.propertyIsEnumerable('p3')); //true
console.log(o1.propertyIsEnumerable('p4')); //false
console.log(o1.propertyIsEnumerable('p5')); //false
```
## Detection schema

| _____________            | in Operator   | hasOwnProperty  | propertyIsEnumerable  |
| -------------------------| ------------- |-----------------|-----------------------|
| Own Enumerable           | true          |true             |true                   |
| Own Not-Enumerable       | true          |true             |false                  |
| Inherited Enumerable     | true          |false            |false                  |
| Inherited Not-enumerable | true          |false            |false                  |
