```html
<form>
    <div>
        <em>Support wikipedia!</em>
    </div>    
    <div>
        <label for='name'>My name is:</label>
        <input type='text' name='name' />
        <span class='error'>Please fill it out</span>
    </div>    
    
    <div>
        <label for='agreement'>I want to be a donor:</label>
        <input type='checkbox' name='agreement' checked='yes' />
    </div>
    
    <div>
        <label for='amount'>I want to donate:</label>
        <select name='amount'>            
            <option value='5'>$5</option>
            <option value='10'>$10</option>
            <option value='100'>$100</option>
            <option value='1000' selected='true'>$1000</option>
        </select>    
    </div>    
    
    <div>
        <input type='radio' name='distrubute' value='0'/><label>Equally</label>
        <input type='radio' name='distrubute' value='1'/><label>To new articles</label>
        <input type='radio' name='distrubute' value='2' checked/><label>To existing articles</label>
    </div>    
    
    <div>
        <input type='reset' value='Reset' />
        <input type='submit' value='Make donation!' />
    </div>    
    
</form>
```

```javascript
// :first is jQuery selector extension. 
// :checkbox and :radio are jQuery form selectors.
// :nth-last-child is jQuery Css selector.
$('form input:checkbox:first').on('change', function(){
    if(this.checked)
    	$('form div:nth-last-child(-n + 3)').show();
    else
        $('form div:nth-last-child(-n + 3)').hide();
});

$('form').on('submit', function(ev){
    var name = $('form input:text:first').val();
    if(!name)
        $('form span.error:first').show();
    else
        $('form span.error:first').hide();
    var amount = $('form select option:selected:first').val();
    var distribute = $('form input:radio:checked:first').next().html().toLowerCase();
    var alert = 'Hi ' + name + '! Please confirm that you want to donate ' + amount + ' dollars '  + distribute;
    console.log(alert);
    return false; // = ev.preventDefault() + ev.stopPropagation();
});

```
