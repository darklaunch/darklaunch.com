# Convert html dropdown element into a textual representation

Convert a set of select options into readable text using JavaScript.

Take a webpage showing a select dropdown

```html
<select>
    <option>- Select -</option>
    <option value="a">Choice 1</option>
    <option value="b">Choice 2</option>
    <option value="c">Choice 3</option>
</select>
```

and convert it into a textual representation:

```
- Select -
Choice 1: a
Choice 2: b
Choice 3: c
```

Step 1. Open Web Developer Tools:
Firefox: `Tools > Browser Tools > Web Developer Tools.`
Chrome: `View > Developer > Developer Tools.`

Step 2: Inspect the html `select` element using the element picker so that the `$0` variable can be used in the JavaScript console.

Step 3: In the JavaScript console, use the following script to display the html select options as text:

```javascript
Array.from($0).map(entry => entry.innerText + (entry.hasAttribute('value') ? ': ' + entry.value : '')).join('\n')
```

When the script is run, the console will display a string representation of the dropdown choices:

```
"- Select -
Choice 1: a
Choice 2: b
Choice 3: c"
```

Step 4: Wrap the code with the `copy()` function to store the resulting string in the clipboard:

```javascript
copy(Array.from($0).map(entry => entry.innerText + (entry.hasAttribute('value') ? ': ' + entry.value : '')).join('\n'))
```

---

Posted Aug 18, 2022.

https://www.darklaunch.com/2022/08/18/convert-html-select-options-to-text.html

---

1 comment

<ol><li><div>

Anon &ndash; Nov 27, 2023<div>

You are genius

</div></div></li></ol>