<code name="php">
header('location: http://example.org');
exit; // !important

// OR SIMPLY

header('location: http://example.org');
exit; // !
</code>

<code name="javascript">
// snippet...
switch(e.keyCode){
    case 13:
        // code for ENTER
        break; // !important
    case 27:
        // code for ESC
        break; // !
}
return true;
</code>