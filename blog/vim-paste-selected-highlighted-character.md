Find and replace the selected character in vim.

Let's suppose you have the following text and you would like to replace bullets with dashes:

```
• First
• Second
• Third
```

Move the cursor over to a bullet using `h`, `j`, `k`, and `l`.

```
• First
^ The cursor should now be here
• Second
• Third
```

Once the cursor is over the bullet, switch to visual mode by typing the `v` character. Then type `y` to yank the character under the cursor and store it in the clipboard. The bullet character is now in the clipboard.

To replace instances of the bullet character, use the find and replace command syntax:

```
:%s/find/replace/g
```

```
:%s/find/replace/g
    ^^^^ This is where we want the yanked character to be pasted
```

Type `:%s/` then enter the bullet character from the clipboard by typing `Ctrl` + `r` and `"`. The command should now look like this so far:

```
:%s/•
```

Then finish the rest of the find and replace command by add a `/`, the replacement string `-`, followed by another `/` and a `g` for global find and replace.

The final command looks like this:

```
:%s/•/-/g
```

With the complete command entered, type `enter` to execute the find and replace.

This will now be the updated text:

```
- First
- Second
- Third
```