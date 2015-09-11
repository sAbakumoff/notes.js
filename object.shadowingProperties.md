#case 1 normal shadowing
```javascript
var o = {p : 1};
var o1 = Object.create(o);
o1.p = 2;
console.log('o.p', o.p); //1
console.log('o1.p', o1.p); //2
```

#case 2 failing shadow
```javascript
var o = {};
Object.defineProperty(o, 'p', {value : 1, writable:false});
var o1 = Object.create(o);
o1.p = 2;
console.log('o.p', o.p); //1
console.log('o1.p', o1.p); //1 or TypeError in 'strict mode'
```

#case 3 ingored shadowing
```javascript
'use strict';
var o = {};
Object.defineProperty(o, 'p', {
    get : function(){
        return 1;
    },
    set : function(value){
        console.log('That is constant value, dude!');
    }
});
var o1 = Object.create(o);
o1.p = 2; // 'That is constant value, dude!'
console.log('o.p', o.p); //1
console.log('o1.p', o1.p); //1
```

#case 4 superior shadowing
```javascript
'use strict';
var o = {};
Object.defineProperty(o, 'p', {
    value : 1,
    writable : false,
    configurable : false
});
var o1 = Object.create(o);
Object.defineProperty(o1, 'p', {value : 2, writable : true});
console.log('o.p', o.p); //1
console.log('o1.p', o1.p); //2
```
