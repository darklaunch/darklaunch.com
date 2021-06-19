# jQuery file selector works in 1.2.6

jQuery file selector works in 1.2.6

$('#myform :file[value!='']') works in 1.2.6, but not in 1.3.x

Selector is looking for inputs of type file with value not empty.

Test case where "uncaught exception: Syntax error, unrecognized expression: value!='']":

```html
<div id="myform">
    <form action="test-selector.php" enctype="multipart/form-data" method="post">
        <div>
            <input type="file" name="file" /><br />
            <input type="file" name="file" /><br />
            <input type="file" name="file" /><br />
            <input type="button" value="Send" onclick="submit_form();" />
        </div>
    </form>
</div>
<!--
<script type="text/javascript" src="js/jquery-1.2.6.js"></script>
-->
<script type="text/javascript" src="js/jquery-1.3.1.js"></script>
<script type="text/javascript">
function submit_form() {
    var files=$('#myform :file[value!=\'\']');
    if (files.length>0) {
        files.each(
            function(i) {
                console.log(this);
            }
        )
    }
    else {
        alert('Select some files please');
    }
}
</script>
```

Why doesn't value expression work in the current release?
RE: http://dev.jquery.com/ticket/4083

> UPDATE: $('#myform :file[value!=\'\']') selector works again with the release of jQuery 1.3.2

---

Posted Feb 5, 2009.

https://www.darklaunch.com/2009/02/05/jquery-file-selector-works-in-1-2-6.html