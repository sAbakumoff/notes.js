```html
<ol id='list-1'>
    <li id='item-1-1'>Business requirements
    <ol id='list-2'>
        <li id='item-2-1'>Business objectives</li>
        <li id='item-2-2'>Success metrics</li>
    </ol></li>
    <li id='item-1-2'>Scope and limitations
    <ol id='list-3'>
        <li id='item-3-1'>Major features</li>
        <li id='item-3-2'>Scope of initial release</li>
    </ol></li>  
</ol>
```

```javascript
// closest(selector, context) - the parameter is required, context limits the search area.
console.log($('#item-3-1').closest('li').attr('id')); // > item-3-1 as search starts from the item

console.log($('#item-3-1').closest('ol').attr('id')); // > list-3

console.log($('#item-3-1').closest('ul').get()); // > [] as no ul's can be found near

// parent(selector)
console.log($('#item-3-1').parent('ol').attr('id')); // > list-3
console.log($('#item-3-1').parent().attr('id')); // > list-3
console.log($('#item-3-1').parent('li').get()); // > []

// parents(selector)
$('#item-3-1').parents().each(function(){
    console.log(this); // list-3, item-1-2, list-1, body, html
});

$('#item-3-1').parents('ol').each(function(){
    console.log(this); // list-3, list-1
});

// parentsUntil(selector, filter) - goes up until selector, but not included, optionally filtering
$('#item-3-1').parentsUntil('li', '#list-3').each(function(){
    console.log(this); // list-3
});
```
