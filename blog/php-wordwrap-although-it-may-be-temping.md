although it may sound like a good idea to use php's wordwrap() for user comments+, use css to control long strings
```php
<?php
// from database, already sanitized
$comment = <<<EOF
this is a reallllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllyyyyyyyyyyyyy long comment that will break the layout..........................................................................................................................................................................................
EOF;
echo 
    '<div class="comment">' .
        $comment .
    '</div>' .
    '';
```
```css
.comment{
    overflow-x: auto;
}
```