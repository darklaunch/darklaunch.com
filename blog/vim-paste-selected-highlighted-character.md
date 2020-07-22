To copy the selected/highlighted character under to cursor to the clipboard, highlight the character in visual mode. Type Ctrl + r followed by typing a double-quote. This will yank the character under the cursor. Paste the character using p.

To replace instances of the yanked character, visual highlight (select) the character or characters you wish to find and replace. Type the character "y" to yank the selection into the clipboard. Now to replace instances of this character: Type ":%s/", then Ctrl + r followed by a double-quote to paste the yanked character. The full command:

```
type :%s/ then type <C-r> + " then /replace/g
":%s/char/replace"
```

The find and replace syntax is:

```
:%s/find/replace/g
    ^^^^ the yanked characters will be pasted here
```

vim paste from system clipboard: "+p