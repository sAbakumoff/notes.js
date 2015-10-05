```javascript
function log(){return console.log(arguments);}
function handleTimeout(timeout){
    var deferred = $.Deferred();
    setTimeout(function(){
        if(timeout % 2 === 0)
        	deferred.resolve(timeout, ' is even');
        else
            deferred.reject(timeout, ' id odd');
    }, timeout);
    return deferred.promise();
}

handleTimeout(10)
    .done(log) // to be called when the Deferred is resolved.
    .done(log); // returns the same deferred object.

handleTimeout(11)
    .fail(log) // to be called when the Deferred is rejected.
    .fail(log); // returns the same deferred object.

handleTimeout(17)
	.always(log) // to be called when the Deferred is either resolved or rejected.
	.always(log); // returns the same deferred object.

handleTimeout(20)
    .then(
    	log, // to be called when the Deferred is resolved.
    	log // to be called when the Deferred is rejected.    
    )
    .then(log); // returns new Deferred object. By default the wrapped 'undefined'

$.when(handleTimeout(50), handleTimeout(56))
	.then(log, log); // to be called when all Deferred's are resolved or rejected
```
