To remove all trailing spaces in vim, use the following command:

```
:%s/ \{1,}\n/\r/gc
```

Explained:

```
: - command
%s - entire selection
/ - separator
 \{1,}\n - search for one or more spaces followed by a newline
/ - separator
\r - replace with a newline
/ - separator
g - global replace
c - confirm replacements (type y (yes) to confirm replacements)
```

---


Posted Sep 6, 2011.
https://www.darklaunch.com/2011/09/06/vim-remove-trailing-spaces.html