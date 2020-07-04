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