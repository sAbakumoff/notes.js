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
console.log("# of LI's on the 1st level is", $('#list-1').children('li').length /*2*/); 

console.log("# of LI's on all the levels is", $('#list-1').find('li').length /*6 */);
```
