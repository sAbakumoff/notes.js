```javascript
function toString(val){
    var jsonVersion = JSON.stringify(val);
    console.log(jsonVersion, typeof jsonVersion);
}

toString(15); // '15' string
toString(true); // 'true' string
toString('abc'); // 'abc' string
toString({}); // '{}' string
toString(null); // 'null' string
toString(undefined); // undefined 'undefined'

toString([1,2,3]); // [1,2,3] string
toString(toString); // undefined 'undefined'

var o = {
    // In other words, toJSON() should be interpreted as "to a JSON-safe value suitable for stringification," not "to a JSON string"
    toJSON : function(){
        return null;
    }
}

toString(o); // 'null' string
```




