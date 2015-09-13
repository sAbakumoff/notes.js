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
# call function with "new" keyword
* new object created
* prototype of the created object is set to function.prototype
* function is called with "this" is bound to the newly created function
* function returns the newly created object
```javascript
function f(){
    this.a = 4;
}
f.prototype = {
    b: 5
}
var o = new f();
console.log(o.a); // 4
console.log(o.b); // 5 through prototype chain
console.log(Object.getPrototypeOf(o) === f.prototype); //true
```
# constructor
```javascript
function f(){
}
console.log(f.prototype.constructor === f); // true

var o = new f();
console.log(o.constructor === f) ; // true through prototype chain

//but
f.prototype.constructor = 'not a ctor';
console.log(o.constructor === f) ; // false through prototype chain

// therefore don't trust the constructor property, it's illusion!
```

# Prototypal Inheritance
it's all about building the prototype chain and using "new" function call
```javascript
function f1(){
    this.a = 4;
}
f1.prototype.getA = function(){
	return this.a;
}

function f2(){
    f1.apply(this, arguments); // here we make sure that f1 call fills the object
    this.b = 5;
}
f2.prototype = Object.create(f1.prototype); // here is we borrow prototype of f1...
f2.prototype.getB = function(){ //...and expand it
    return this.b;
}

var o = new f2();
```
# Orphaned object - the one that has no ancestors!
```javascript
var o = Object.create(null);
console.log(Object.getPrototypeOf(o));
```
# instanceof and isPrototypeOf
```javascript
function f(){}
function g(){}
var fp = Object.create(f.prototype);
g.prototype = fp;
var o = new g();
console.log(o instanceof g); //true because o.[[Prototype]] = g.prototype;
console.log(o instanceof f); // true because g.[[Prototype]] = fp; and fp.[[Prototype]] = f.prototype
console.log(o instanceof Object); // true //because f.prototype = Object.prototype

console.log(g.prototype.isPrototypeOf(o)); // true
console.log(f.prototype.isPrototypeOf(o)); // true
console.log(Object.prototype.isPrototypeOf(o)); // true
```

