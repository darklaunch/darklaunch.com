The textarea or input. This is inline via onkeydown.

```html
<textarea cols="50" onkeydown="return interceptTabs(event,this);" rows="15"></textarea>
```

The javascript

```javascript
function interceptTabs(evt,control){
	key=evt.keyCode?evt.keyCode:evt.which?evt.which:evt.charCode;
	if(key==9){
		insertAtCursor(control,'t');
		return false;
	}
	else{
		return key;
	}
}
function insertAtCursor(myField, myValue){
	if(document.selection){
		/* ie */
		myField.focus();
		sel=document.selection.createRange();
		sel.text=myValue;
	}
	else if(myField.selectionStart||myField.selectionStart=='0'){
		/* mozilla support */
		var startPos=myField.selectionStart;
		var endPos=myField.selectionEnd;
		restoreTop=myField.scrollTop;
		myField.value=myField.value.substring(0,startPos)+myValue+myField.value.substring(endPos,myField.value.length);
		myField.selectionStart=startPos+myValue.length;
		myField.selectionEnd=startPos+myValue.length;
		if(restoreTop>0){
			myField.scrollTop=restoreTop;
		}
	}
	else{
		myField.value+=myValue;
	}
}
```

EDIT: see the jQuery version of this http://darklaunch.com/2009/02/03/javascript-insert-tabs-into-textarea-insert-tabs-into-input-javascript-tab-indent

---


Posted Feb 3, 2009.
https://www.darklaunch.com/2009/02/03/javascript-tab-inserts-tab-how-to-insert-an-actual-tab-in-an-input-or-textarea.html