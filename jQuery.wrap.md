```html
<li id='item-1-1'>Business requirements</li>
<li id='item-1-2'>Scope and limitations</li>  
```

```javascript
$('li').wrapAll('<ol></ol>'); // <ol>li li</ol>
$('li').wrap('<ul></ul>'); // <ol><ul>li</ul> <ul>li</ul></ol>
$('li').unwrap(); // <ol>li li</ol>
$('li').wrapInner('<i></i>'); // <ol><li><i>..</i></li> <li><i>..</i></li></ol>
```
