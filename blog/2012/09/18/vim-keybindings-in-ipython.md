# Vim keybindings in ipython

To set vim keybindings in ipython, do the following:

Add the following `set` commands in your `~/.inputrc` file:

```bash
set editing-mode vi
set keymap vi-insert
```

```bash
echo -e "\n# Vim keybindings\nset editing-mode vi\nset keymap vi-insert" >> ~/.inputrc
```

editing-mode controls the key bindings used.

keymap controls readline's key bindings.

---

Posted Sep 18, 2012.

https://www.darklaunch.com/2012/09/18/vim-keybindings-in-ipython.html