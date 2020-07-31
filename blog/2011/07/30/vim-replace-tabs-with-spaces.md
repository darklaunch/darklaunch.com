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

---


Posted Jul 30, 2011.
https://www.darklaunch.com/2011/07/30/vim-replace-tabs-with-spaces.html