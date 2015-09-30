```html
<p>Look. If you had one shot or one opportunity</p>
<p>To seize everything you ever wanted</p>
<p>One moment</p>
```

```javascript
// switch 1st and 3rd line by using replace methods:
var thirdLine = $('p').eq(2).clone();
$('p').eq(2).replaceWith($('p:first').clone());
$('p:first').replaceWith(thirdLine);
```
