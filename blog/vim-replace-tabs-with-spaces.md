To replace all tabs with 4 spaces in vim using the following command:
```
:%s/\t/    /g
```

Explained:
```
: - command
%s - entire selection
/ - separator
\t - search for tab
/ - separator
"    " - replace with 4 spaces
/ - separator
g - global replace
```