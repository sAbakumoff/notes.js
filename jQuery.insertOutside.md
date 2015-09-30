```html
<p>Look. If you had one shot or one opportunity</p>
```

```javascript
$('p').before('Eminem.');
$('<em>Lose yourself</em>').insertBefore('p');

$('<span>ONE MOMENT</span>').insertAfter('p');
$('p').after('To seize everything you ever wanted');
// the result is 
// Eminem.Lose yourself
//Look. If you had one shot or one opportunity
//To seize everything you ever wantedONE MOMENT
```
