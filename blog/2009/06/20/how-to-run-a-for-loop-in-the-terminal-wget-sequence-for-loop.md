This will download a sequence of pictures from picture1.jpg to picture10.jpg from example.com:

```bash
for i in $(seq 10); do wget "http://example.com/folder/picture$i.jpg"; done
```

---


Posted Jun 20, 2009.
https://www.darklaunch.com/2009/06/20/how-to-run-a-for-loop-in-the-terminal-wget-sequence-for-loop.html