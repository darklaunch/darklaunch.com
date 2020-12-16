Join two tabs (also called panes) in Byobu by calling running a tmux command.

Call the Byobu tmux prefix (`Ctrl` + `a`) followed by a colon.

```bash
Ctrl + a + :
```

At the prompt, run the `join-pane` command with the source panel using the `-s` flag.

```bash
:join-pane -s 2
```

This will split the current window horizontally with the current window in the top and the window in position 2 in the bottom.

```
     join-pane [-bdhv] [-l size | -p percentage] [-s src-pane] [-t dst-pane]
                   (alias: joinp)
             Like split-window, but instead of splitting dst-pane and creating a new pane, split it and move
             src-pane into the space.  This can be used to reverse break-pane.  The -b option causes src-pane
             to be joined to left of or above dst-pane.
```

---

Posted Mar 26, 2018.

https://www.darklaunch.com/2018/03/26/byobu-join-two-tabs.html