PHP File Upload Error Codes

```php
// UPLOAD_ERR_OK         Value: 0
// There is no error, the file uploaded with success.

// UPLOAD_ERR_INI_SIZE   Value: 1
// The uploaded file exceeds the upload_max_filesize directive in php.ini.

// UPLOAD_ERR_FORM_SIZE  Value: 2
// The uploaded file exceeds the MAX_FILE_SIZE directive that was specified in the HTML form.

// UPLOAD_ERR_PARTIAL    Value: 3
// The uploaded file was only partially uploaded.

// UPLOAD_ERR_NO_FILE    Value: 4
// No file was uploaded.

// UPLOAD_ERR_NO_TMP_DIR Value: 6
// Missing a temporary folder. Introduced in PHP 4.3.10 and PHP 5.0.3.

// UPLOAD_ERR_CANT_WRITE Value: 7
// Failed to write file to disk. Introduced in PHP 5.1.0.

// UPLOAD_ERR_EXTENSION  Value: 8
// A PHP extension stopped the file upload. Introduced in PHP 5.2.0.
```

```php
<?php
error_reporting(E_ALL | E_STRICT);
ini_set('display_errors', 1);

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $name     = $_FILES['myfile']['name'];
    $type     = $_FILES['myfile']['type'];
    $tmp_name = $_FILES['myfile']['tmp_name'];
    $error    = $_FILES['myfile']['error'];
    $size     = $_FILES['myfile']['size'];
    
    switch ($error) {
        case UPLOAD_ERR_OK:
            $response = 'There is no error, the file uploaded with success.';
            break;
        case UPLOAD_ERR_INI_SIZE:
            $response = 'The uploaded file exceeds the upload_max_filesize directive in php.ini.';
            break;
        case UPLOAD_ERR_FORM_SIZE:
            $response = 'The uploaded file exceeds the MAX_FILE_SIZE directive that was specified in the HTML form.';
            break;
        case UPLOAD_ERR_PARTIAL:
            $response = 'The uploaded file was only partially uploaded.';
            break;
        case UPLOAD_ERR_NO_FILE:
            $response = 'No file was uploaded.';
            break;
        case UPLOAD_ERR_NO_TMP_DIR:
            $response = 'Missing a temporary folder. Introduced in PHP 4.3.10 and PHP 5.0.3.';
            break;
        case UPLOAD_ERR_CANT_WRITE:
            $response = 'Failed to write file to disk. Introduced in PHP 5.1.0.';
            break;
        case UPLOAD_ERR_EXTENSION:
            $response = 'File upload stopped by extension. Introduced in PHP 5.2.0.';
            break;
        default:
            $response = 'Unknown upload error';
            break;
    }
    
    echo $response;
} else {
    echo
        '<form action="upload.php" enctype="multipart/form-data" method="post">' .
            '<input name="myfile" type="file" />&lt;br />' .
            '<input type="submit" value="Submit" />' .
        '</form>' .
        '';
}
```

---

Posted May 1, 2009.

https://www.darklaunch.com/2009/05/01/php-file-upload-error-codes-upload-err-ok.html

---

4 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Sep 7, 2010
            <div>
                <p>hi, i try your script n i get error "Failed to write file to disk. Introduced in PHP 5.1.0."</p><p></p><p>what should i do to fix that..?? </p><p>my folder cmod already set to 7777...</p><p></p><p>thx,</p><p></p><p>opick</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 8, 2010
            <div>
                <p>make sure error reporting is on which may provide further detail:</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<code>error_reporting(E_ALL | E_STRICT);</code></p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<code>ini_set('display_errors', 1);</code></p><p></p><p>also, check out</p><p><a href="http://us.php.net/manual/en/features.file-upload.common-pitfalls.php">http://us.php.net/manual/en/features.file-upload.common-pitfalls.php</a></p><p><a href="http://us.php.net/manual/en/features.file-upload.errors.php">http://us.php.net/manual/en/features.file-upload.errors.php</a></p><p><a href="http://us.php.net/manual/en/features.file-upload.post-method.php">http://us.php.net/manual/en/features.file-upload.post-method.php</a></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 8, 2010
            <div>
                <p><code>UPLOAD_ERR_CANT_WRITE</code> sometimes means ran out of disk space on the temporary upload location.</p><p></p><p>check the available diskspace on <code>/tmp</code></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 18, 2014
            <div>
                <p>If security is an issue, you must never reply on <code>$_FILES['myfile']['type']</code> as this can be modified by a naughty person. Instead, use <code>exif_imagetype($_FILES["myfile"]["tmp_name"])</code>.</p>
            </div>
        </div>
    </li>
</ol>
