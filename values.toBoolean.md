```javascript
function boolConversion(val){
    if(val){
        console.log('not falsy');
    }
    else{
        console.log('falsy');
    }
}
boolConversion(undefined); // falsy
boolConversion(null); // falsy
boolConversion(false); // falsy
boolConversion(NaN); // falsy
boolConversion(0); // falsy
boolConversion(''); // falsy
               
boolConversion(true); // non falsy
boolConversion(0.5); // non falsy
// and everything else is not falsy...
```
