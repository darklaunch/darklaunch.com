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

---

Posted Jun 10, 2010.

https://www.darklaunch.com/2010/06/10/javascript-get-input-caret-cursor-position-getselectionstart-getselectionend-char-position.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Sep 7, 2012
            <div>
                <p>wtf is o</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 7, 2012
            <div>
                <p>@wtf o is object</p>
            </div>
        </div>
    </li>
</ol>
