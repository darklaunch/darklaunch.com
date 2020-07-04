To upload a file using the command line, do the following:
```
curl "https://example.com/upload.php" -F myfile=@"/path/to/file"
```
Example:
```
curl "https://example.com/upload.php" -F myfile=@"~/Desktop/image.png"
```
And using authentication:
```
curl -u username:password "https://example.com/upload.php" -F myfile=@"~/Desktop/image.png"
```
NOTE:
Change myfile to the file input value name.
&lt;input name="myfile" type="file" />
```php
// upload.php
var_dump($_POST);
var_dump($_FILES);
```