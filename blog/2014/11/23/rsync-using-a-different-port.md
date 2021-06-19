# rsync using a different port

Specify a different ssh port when using rsync.

```sh
rsync --rsh="ssh -p 2222" /path/to/src/ user@host:/path/to/dest/
```

An example with more options added.

```sh
time rsync \
    --compress \
    --progress \
    --recursive \
    --rsh="ssh -p 2222 -i ~/.ssh/path/to/id_rsa" \
    --verbose \
    --partial \
    /path/to/src/ \
    user@host:/path/to/dest/
```

---

Posted Nov 23, 2014.

https://www.darklaunch.com/2014/11/23/rsync-using-a-different-port.html