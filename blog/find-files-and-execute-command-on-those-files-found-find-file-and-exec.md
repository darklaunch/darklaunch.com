To find files and execute a command on the files found, do the following:
```
cd /path/to/directory
find ./ ! -iname "*.mp3" -type f -exec echo {} \;
```

The above command finds any non-mp3 (! -iname *.mp3) file (-type f) in the current directory (./) and prints the file found (-exec echo {}). The curly brackets are replaced with the found files. "\;" signals the end of the command to execute.

The tests may be chained to together:
```
find ./ ! -iname "*.mp3" ! -iname "*.m3u" ! -iname "*.pls" -type f -exec echo {} \;
```

To remove or perform another action on the files found, change the exec action. The following will remove the files found:
```
find ./ ! -iname "*.mp3" ! -iname "*.m3u" ! -iname "*.pls" -type f -exec rm {} \;
```