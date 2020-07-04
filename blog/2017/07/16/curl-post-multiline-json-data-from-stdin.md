POST json data with Curl from the command line via STDIN.
```bash
$ curl https://api.example.com/posts/create --data @- <<REQUEST_BODY
{
    "title": "Hello world!",
    "content": "This is my first post."
}
REQUEST_BODY
```
```php
<?php
$data = json_decode(file_get_contents('php://input'));
var_dump($data);
```

Response
```
object(stdClass)#1 (2) {
  ["title"]=>
  string(12) "Hello world!"
  ["content"]=>
  string(22) "This is my first post."
}
```