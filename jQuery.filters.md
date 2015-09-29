```html
<p>Mary had a little lamb,</p>
<p>Its fleece was white as snow,</p>
<p>And every where that Mary went</p>
<p>The lamb <i>was sure</i> to go;</p>
<p>He followed her to school one day—</p>
<p>That was against the rule,</p>
<p>It made the children laugh and play,</p>
<p>To see a lamb at school.</p>
```

```javascript
// indices-based selection:
$('p').first().css('color', 'red');
$('p').last().css('color', 'blue');
$('p').slice(1,2).css('color', 'green');
$('p').slice(-2,-1).css('color', 'orange');
$('p').eq(2).css('color', 'gold');

// selector-based selection
$('p').filter(':even').css('font-size', '25px');
$('p').not(':even').css('font-size', '10px');

// has descendants:
$('p').has('i').css('background', 'whitesmoke');

// map:
console.log($('p').map(function(index, element){
    return $(this).text();
}).get()); // array that consists of the Mary Lamb poem lines.

// is : the same as has, but returns true value instead of jQuery object!
console.log($('p').is(':even')); // true
```

The result can be found at http://jsfiddle.net/3max9zwu/
