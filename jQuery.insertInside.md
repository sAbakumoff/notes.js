```html
<p>Look. If you had one shot or one opportunity</p>
<div></div>
<span></span>
```

```javascript

$('p').append(' to seize everything you ever wanted.', 'One moment.');
$('Would you capture it').appendTo('p');

$('p').prepend('Loose yourself: ');
$('<em>Eminem.</em>').prependTo('p');

// The final result is p with the following content:
// Eminem.Loose yourself: Look. If you had one shot or one opportunity to seize everything you ever wanted.One moment.

$('div').html('<i>verse one</i>');
$('span').text('To be continued...');

```
