Rename a Byobu tab using the tmux rename-window command. Example:

```bash
$ tmux rename-window -t 0 "My Tab at position 0"
```

Rename the current tab using the environment variable `$TMUX_PANE`.

```bash
$ tmux rename-window -t "${TMUX_PANE}" "My Awesome Tab"
```

Usage for tmux rename-window:

```bash
$ tmux rename-window
usage: rename-window [-t target-window] new-name
```

---

Posted Jul 26, 2017.
https://www.darklaunch.com/2017/07/26/rename-byobu-tab