```javascript
function toString(val){
    if(val !== null && typeof val !== 'undefined'){
		console.log(val.toString(), Object.prototype.toString.call(val));
    }
    else{
        console.log(val + '');
    }
}

toString(15); // '15'  [object Number]
toString(true); // 'true' [object Boolean]
toString('abc'); // 'abc' [object String]
toString({}); // [object Object] [object Object]
toString(null); // 'null'
toString(undefined); // 'undefined'

toString([1,2,3]); // 1,2,3 [object Array]
toString(toString); // *toString body* [object Function]


function toString2(val){
    var val = String(val);
    console.log(val, typeof val);
}

toString2(null); // 'null' string
toString2(undefined); // 'undefined' string
toString2(12); // '12' string
toString2(false); // 'false' string
toString2([1,2,3]); // 1,2,3 string
toString2(toString2); // *toString body* string

```
