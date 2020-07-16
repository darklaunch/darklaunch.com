To get the input field character position using JavaScript, use the following:
```js
function getSelectionStart(o) {
    if (o.createTextRange) {
        var r = document.selection.createRange().duplicate();
        r.moveEnd("character", o.value.length);
        if (r.text == "") {
            return o.value.length;
        }
        else {
            return o.value.lastIndexOf(r.text);
        }
    }
    else {
        return o.selectionStart;
    }
}

function getSelectionEnd(o) {
    if (o.createTextRange) {
        var r = document.selection.createRange().duplicate();
        r.moveStart("character", -o.value.length);
        return r.text.length;
    }
    else {
        return o.selectionEnd;
    }
}
```