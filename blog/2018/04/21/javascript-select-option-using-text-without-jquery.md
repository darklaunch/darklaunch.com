To select an option by searching for the option's text value without jQuery, use the filter method.

```html
<select>
    <option>Select an option...</option>
    <option value="1">Alpha</option>
    <option value="2">Bravo</option>
    <option value="3">Charlie</option>
</select>
```

Select all the options using document.querySelectorAll. Then filter by matching the innerText.

```javascript
var bravoChoice = Array.from(document.querySelectorAll('option'))
    .filter(option => option.innerText === 'Bravo')[0];
bravoChoice.selected = true;
```

---

Posted Apr 21, 2018.

https://www.darklaunch.com/2018/04/21/javascript-select-option-using-text-without-jquery.html