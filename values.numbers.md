# Representation in code
```javascript
var a = 11, b = 11., c = 11.00;
console.log(a === b); // true
console.log(a === c ); // true

var d = .11, e = 0.11;
console.log(d === e ); // true

var h = 0xff, h10 = 255;
console.log(h === h10); //0x starts the hex numbers

var o = 0o377, o10 = 255;
console.log(o === o10); //0o starts the oct numbers

var b = 0b11111111, b10 = 255; //0b starts the binary numbers
```

# Small Numbers
```javascript
console.log(0.1 + 0.2 === 0.3); // false
//use epsilon to compare the small numbers:
function compare(a, b){
    var epsilon = Math.pow(2, -52);
    return Math.abs(a-b) < epsilon;
}
console.log(compare(0.1 + 0.2, 0.3)); // true
console.log(compare(0.1, 0.2)); // false
```

# Test for integer
```javascript
function isInteger(num){
    return typeof num === 'number' && num % 1 === 0;
}

console.log(isInteger(12)); // true
console.log(isInteger(12.21)); // true
```

# Bitwise operations
only for 32-bit signed integers, use a | 0 to get such an integer
