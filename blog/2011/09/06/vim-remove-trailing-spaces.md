# Vim remove trailing spaces

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

---

2 comments

<ol><li><div>

anonymous &ndash; May 22, 2013<div>

Why don't you use 
:%s/ \+\n/\r/gc

</div></div></li><li><div>

anonymous &ndash; Jun 7, 2013<div>

@"Why don't you use"

both work. which one reads more clearly?

</div></div></li></ol>