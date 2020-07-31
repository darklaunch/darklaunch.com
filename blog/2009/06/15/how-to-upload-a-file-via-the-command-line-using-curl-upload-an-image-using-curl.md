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

---


Posted Jun 15, 2009.
https://www.darklaunch.com/2009/06/15/how-to-upload-a-file-via-the-command-line-using-curl-upload-an-image-using-curl.html