To replace all 2 space indentations, use the following command:
```
:%s/\n \{2\}\([^ ]\)/\r    \1/gc
```
Explained:
```
: - command
%s - entire selection
/ - separator
\n \{2\}\([^ ]\) - search for a newline and 2 spaces followed by a character that is not a space
/ - separator
\r    \1 - replace with a newline and the matching group that is a not a space
/ - separator
g - global replace
c - confirm replacements (type y (yes) to confirm replacements)
```