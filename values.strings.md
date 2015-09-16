#Access to individual characters
```javascript
var str = 'abc';
console.log(str[0]); // does not work in the old versions of IE
console.log(str.charAt(0)); // works everywhere, use it, use it, use it
```
#Immutability
```javascript
str[0] = 'D'; // does not have any effect because strings are immutable!

//  since strings are immutable, it might be required to work with array of chars instead:
function reverseString(str){
    if(typeof str !== 'string'){
        return str;
    }
    var charsArray = str.split('');
    for(var i = 0; i < charsArray.length / 2; i++){
        var t = charsArray[i];
        charsArray[i] = charsArray[charsArray.length - 1 - i];
        charsArray[charsArray.length - 1 - i] = t;
    }
    return charsArray.join(''); // or charsArray.reverse().join('');
}

```
