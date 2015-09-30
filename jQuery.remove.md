```html
<p>Look. If you had one shot or one opportunity</p>
<p>To seize everything you ever wanted</p>
<p>One moment</p>
```

```javascript
$('p:first').remove();
var secondLine = $('p:first').detach();
$('p').empty();
$('p').before(secondLine);

// the result is the 2nd p inserted before the 3rd one
//<p>To seize everything you ever wanted</p>
//<p></p>
```
