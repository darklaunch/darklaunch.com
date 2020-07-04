<p>To select an option by searching for the option's text value without jQuery, use the filter method.</p>

<code name="html">
<select>
    <option>Select an option...</option>
    <option value="1">Alpha</option>
    <option value="2">Bravo</option>
    <option value="3">Charlie</option>
</select>
</code>

<p>Select all the options using document.querySelectorAll. Then filter by matching the innerText.</p>

<code name="javascript">
var bravoChoice = Array.from(document.querySelectorAll('option'))
    .filter(option => option.innerText === 'Bravo')[0];
bravoChoice.selected = true;
</code>