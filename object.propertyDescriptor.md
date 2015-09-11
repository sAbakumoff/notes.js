#Object.defineProperty 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperties
```javascript
var o = {

}
Object.defineProperty(o, 'p', {
    value : 5, // default is undefined
    writable : false, // the value can be changed, default is FALSE
    configurable : false, // the property can be deleted or descriptor modified, default is FALSE
    enumerable : true, // if it's appears in enumeration, default is FALSE
});

Object.defineProperty(o, 'p1', {
    get : function(){ // "value" is ignored, RHS expressions call get()
        return 'a';
    },
    set : function(value){ // "writable" is ignored, LHS expressions will call set()
        console.log('the setter has been called, but it does nothing actually');
    }
});

o.p2 = 'abc';

for(var prop in o){
    console.log(prop); // p, p2 but not p1 as it's not enumerable!
}
```

#Object.getOwnPropertyDescriptor
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor
```javascript
var desc = Object.getOwnPropertyDescriptor(o, 'p2');
console.log(desc.value);
console.log(desc.writable);
console.log(desc.enumerable);
console.log(desc.configurable);
```
