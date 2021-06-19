# Byobu move tabs with tmux shortcut

Set tmux shortcuts in Byobu to move tabs left and right.

```
# Move current tab to the right with ctrl + shift + right.
bind-key -n C-S-Right swap-window -t +1

# Move current tab to the left with ctrl + shift + left.
bind-key -n C-S-Left swap-window -t -1
```

The tmux configuration for Byobu is located under
```
~/.byobu/.tmux.conf
```

Press `F5` to refresh without restarting Byobu.

Move tabs in Byobu without setting shortcuts:

Move current tab to the right:
```
Ctrl + A, :swap-window -t +1
```

Move current tab to the left:
```
Ctrl + A, :swap-window -t -1
```

List all key bindings using the list-keys command:
```
$ tmux list-keys
```

---

Posted Feb 11, 2018.

https://www.darklaunch.com/2018/02/11/byobu-move-tabs-with-tmux-shortcut.html