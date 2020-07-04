```php
header('Location: https://example.org');
exit; // !important

// OR SIMPLY

header('Location: https://example.org');
exit; // !
```

```javascript
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
```