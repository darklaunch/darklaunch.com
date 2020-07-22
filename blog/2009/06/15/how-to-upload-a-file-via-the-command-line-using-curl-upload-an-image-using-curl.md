To upload a file using the command line, do the following:

```bash
$ curl "https://www.example.com/upload.php" -F myfile=@"/path/to/file"
```

Example:

```bash
$ curl "https://www.example.com/upload.php" -F myfile=@"~/Desktop/image.png"
```

And using authentication:

```bash
$ curl -u username:password "https://www.example.com/upload.php" -F myfile=@"~/Desktop/image.png"
```

NOTE:
Change myfile to the file input value name.
```html
&lt;input name="myfile" type="file" />
```

```php
// upload.php
var_dump($_POST);
var_dump($_FILES);
```