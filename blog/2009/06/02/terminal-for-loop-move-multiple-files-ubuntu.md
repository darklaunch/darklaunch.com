To move files using a for loop, do the following:

```bash
cd /path/to/files/directory
for i in *.txt; do mv $i ~/Desktop/destination/$i; done
```

The above code will move files with a txt extension to the destination folder on the desktop.

---

Posted Jun 2, 2009.
https://www.darklaunch.com/2009/06/02/terminal-for-loop-move-multiple-files-ubuntu