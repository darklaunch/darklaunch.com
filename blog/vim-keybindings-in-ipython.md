To set vim keybindings in ipython, do the following:

Add the following `set' commands in your ~/.inputrc

```
set editing-mode vi
set keymap vi-insert```

```echo -e "\n# Vim keybindings\nset editing-mode vi\nset keymap vi-insert" >> ~/.inputrc```

editing-mode controls the key bindings used.

keymap controls readline's key bindings.