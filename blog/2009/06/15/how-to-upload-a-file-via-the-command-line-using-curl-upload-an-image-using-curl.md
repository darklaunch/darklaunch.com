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

---

4 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Dec 8, 2012
            <div>

When I try this, I just get the message:   array(0)
Any ideas?!  Thanks!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 9, 2012
            <div>

@array(0)

try var_dump($_POST) and var_dump($_GET); to see if at least something is coming through

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 16, 2013
            <div>

Thanks :) .. it helped.

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 30, 2017
            <div>

was about to pull my hair out. Stumbled upon your page. Works perfectly.

            </div>
        </div>
    </li>
</ol>
