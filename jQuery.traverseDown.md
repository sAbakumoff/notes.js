```html
<ol id='list-1'>
    <li>Business requirements
    <ol>
        <li>Business objectives</li>
        <li>Success metrics</li>
    </ol></li>
    <li>Scope and limitations
    <ol>
        <li>Major features</li>
        <li>Scope of initial release</li>
    </ol></li>  
</ol>
```

```javascript
// children only goes through the 1st level
console.log("# of LI's on the 1st level is", $('#list-1').children('li').length /*2*/); 

// find traverses all the tree levels
console.log("# of LI's on all the levels is", $('#list-1').find('li').length /*6 */);

// passing a context to the 2nd argument of $ sets the element to search within
console.log("# of LI's on starting under list-3 is", $('li', $('#list-3') ).length /* 2 */);

// contents() also returns text and comments nodes as well as hmtl elements.
console.log($('li:first').contents().get()); // ['Business requirements', ol#list-2]
```
