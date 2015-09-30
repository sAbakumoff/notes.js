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
        <li id='item-3-3'>Limitations <i>and exclusions</i></li>
    </ol></li>  
</ol>
```
```javascript
// andSelf() adds the prev element in stack to the collection
console.log($('#item-2-1').next().andSelf().get()); // [li#item-2-1, li#item-2-2]

//end() rolls back the stack to the prev state
console.log($('#item-3-1').nextAll().end().get()); // [li#item-3-1]

//add() adds the given element into the set
console.log($('#item-3-2').next().add('#item-2-1').get()); // [li#item-2-1, li#item-3-3]

//addBack() adds the prev element in the stack to the collection
console.log($('#item-3-2').next().addBack().get()); // [li#item-3-2, li#item-3-3]
```
