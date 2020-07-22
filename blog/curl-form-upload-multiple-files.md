Upload more than 1 file using curl.

```bash
curl \
    --request POST \
    "http://127.0.0.1:8000/" \
    --form "foo=bar" \
    --form "attachment[]=@/path/to/file1.txt" \
    --form "attachment[]=@/path/to/file2.txt"
```
The brackets used in this first request are shorthand for indexing the multiple files. "file1.txt" will be processed as attachment[0]. "file2.txt" will be processed as attachment[1].

```bash
curl \
    --request POST \
    "http://127.0.0.1:8000/" \
    --form "foo=bar" \
    --form "attachment[0]=@/path/to/file1.txt" \
    --form "attachment[1]=@/path/to/file2.txt"
```
Note that the content-length header POSTed in this second request will be greater by 2 bytes. The 2 extra bytes come from the numbers "0" and "1" inside the square brackets that are explicitly included in the request.

Here is the equivalent html form:
```html
<form
    action="http://127.0.0.1:8000/"
    enctype="multipart/form-data"
    method="post">
    <input type="text" name="foo" value="bar" />
    <input type="file" name="attachment[]" />
    <input type="file" name="attachment[]" />
    <input type="submit" />
</form>
```