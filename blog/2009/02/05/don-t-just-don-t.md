don't use short open tags: <? ?>; always use the long form of the PHP open tag (<?php ?>)

don't use print; use echo
```php
<?
// bad
print $var;
?>

<?php
// good
echo $var;
?>
```