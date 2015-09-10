#for (variable in object) {...}
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in
goes through enumerable properties of the specific object, using prototype chain

#Object.getOwnPropertyNames
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyNames
goes through enumerable and non-enumerable properties attached to object itself

#Object.keys
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys
goes through enumerable properties attached to the object itself

```javascript
var o = {
    p : 'source'
}

var o1 = Object.create(o);
o1.p1 = 'abc';

var o2 = Object.create(o1);
o2.p2 = 'xyz';
Object.defineProperty(o2, 'p3', {value : 'qwe', enumerable:false});

for(var p in o2){
    console.log(p + ' = ' + o2[p]); // p = 'source', p1 = 'abc', p2 = 'xyz'
}

var ownProps = Object.getOwnPropertyNames(o2);
for(var i = 0; i < ownProps.length; i++){
    console.log(ownProps[i] + ' = ' + o2[ownProps[i]]); // p2 = 'xyz', p3='qwe'
}

var objectKeys = Object.keys(o2);
for(var i = 0; i < objectKeys.length; i++){
    console.log(objectKeys[i] + ' = ' + o2[objectKeys[i]]); // p2 = 'xyz'
}
```

## Detection schema

| _____________            | for..in       | Object.keys     | getOwnPropertyNames   |
| -------------------------| ------------- |-----------------|-----------------------|
| Own Enumerable           | true          |true             |true                   |
| Own Not-Enumerable       | false         |false            |true                   |
| Inherited Enumerable     | true          |false            |false                  |
| Inherited Not-enumerable | false         |false            |false                  |
