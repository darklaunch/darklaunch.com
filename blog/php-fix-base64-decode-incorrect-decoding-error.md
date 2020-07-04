Fix a garbled base64 decoded string by trying this base64 url decoder:

```php
<?php
function base64url_decode($base64url) {
    // atob(s.replace(/-/g, '+').replace(/_/g, '/'));
    $base64 = strtr($base64url, '-_', '+/');
    $plain_text = base64_decode($base64);
    return $plain_text;
}
```

Why? The mapping table of the base64 implementations vary. For example, the Gmail API uses "-" and "_" as the last two characters (RFC 4648).

https://en.wikipedia.org/wiki/Base64#Implementations_and_history

Keywords: base64, base64_encode, base64_decode, atob, btoa, JavaScript