How to insert tabs and auto-indent using jQuery.

```html
<textarea cols="50" id="mytextarea" rows="15"></textarea>
```

Case 13 is the indenting.
```javascript
$(document).ready(function(){
	$('#mytextarea').keydown(
		function(e){
			if(this.setSelectionRange){
				var start=this.selectionStart,val=$(this).val();
				switch(e.keyCode){
					case 9: /* tab */
						$(this).val(val.substring(0,start)+'t'+val.substr(this.selectionEnd));
						this.setSelectionRange(start+2,start+2);
						this.focus();
						e.preventDefault();
						return false;
						break;
					case 13: /* enter */
						var match=val.substring(0,start).match(/(^|n)([ t]*)([^n]*)$/);
						if(match){
							var spaces=match[2],length=spaces.length+1;
							$(this).val(val.substring(0,start)+'n'+spaces+val.substr(this.selectionEnd));
							this.setSelectionRange(start+length,start+length);
							this.focus();
							return false;
						}
						break;
				}
				return true;
			}
		}
	);
});
```

---

Posted Feb 3, 2009.

https://www.darklaunch.com/2009/02/03/javascript-insert-tabs-into-textarea-insert-tabs-into-input-javascript-tab-indent.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Aug 12, 2013
            <div>
                <p>thanks for this :D</p>
            </div>
        </div>
    </li>
</ol>
