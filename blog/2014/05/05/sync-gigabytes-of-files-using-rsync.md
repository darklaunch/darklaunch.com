Use rsync to sync gigabytes, terabytes of files.

```sh
# sync.sh
time rsync \
    --compress \
    --progress \
    --recursive \
    --verbose \
    --size-only \
    --partial \
    /path/to/source/ \
    user@127.0.0.1:/path/to/destination/
```

```sh
# run.sh
while :; do date; bash sync.sh; sleep 1; done
```

---

Posted May 5, 2014.
https://www.darklaunch.com/2014/05/05/sync-gigabytes-of-files-using-rsync