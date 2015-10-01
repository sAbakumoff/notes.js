```html
<div id='div-1'>
    <div class='red small' style='bottom:0px;'></div>
    <div class='blue medium' style='right:0px;'></div>
</div>
```

```javascript
$("<div class='blue small'></div>").appendTo('#div-1');

// DELEGATED EVENT:
// Occurs only for inner elements of(#div-1) that match the selector(div.blue)
// Occurs for existing and the later added elements
$('#div-1').on('click', 'div.blue', function(ev){
    console.log(this);
});
```
