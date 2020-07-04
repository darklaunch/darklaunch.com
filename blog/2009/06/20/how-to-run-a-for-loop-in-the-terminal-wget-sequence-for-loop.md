This will download a sequence of pictures from picture1.jpg to picture10.jpg from example.com:

```bash
for i in $(seq 10); do wget "http://example.com/folder/picture$i.jpg"; done
```