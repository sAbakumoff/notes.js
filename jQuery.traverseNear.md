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
        <li id='item-3-3'>Limitations and exclusions</li>
    </ol></li>  
</ol>
```

```javascript
// next(selector) returns immediate next elem only
console.log($('#item-3-1').next().get()); // [item-3-2]
console.log($('#item-3-1').next('ul').get()); // []

//nextAll(selector) returns all the next siblings
console.log($('#item-3-1').nextAll().get()); // [item-3-2, item-3-3]
console.log($('#item-3-1').nextAll('#item-3-3').get()); // [item-3-3]

//nextUntil(selector, filter) goes next sublings until the selector match
console.log($('#item-3-1').nextUntil('#item-3-3').get()); // [item-3-2] 

// the same for previous sublings : prev, prevAll, prevUntil

// siblings(selectors) find all next and prev elems and optionally filters them using selector
console.log($('#item-3-2').siblings().get()); // [item-3-1, item-3-3] 

```
