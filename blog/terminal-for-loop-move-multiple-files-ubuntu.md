To move files using a for loop, do the following:
```
cd /path/to/files/directory
for i in *.txt; do mv $i ~/Desktop/destination/$i; done
```
The above code will move files with a txt extension to the destination folder on the desktop.