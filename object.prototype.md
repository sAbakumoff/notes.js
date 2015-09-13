# obj.[[Prototype]]
either null or reference to another object:
```javascript
var o = {
    toString : function(){return 'object o';}
}
var o1 = Object.create(o);
var __proto__;
while((__proto__=Object.getPrototypeOf(o1))!==null){
    console.log(__proto__.toString());
    o1 = __proto__;
}
// object o <- returned from toString of o which is prototype of o1
// [object Object] <- return from toString of Object.prototype which is prototype of Object
```
