<p>To set vim keybindings in ipython, do the following:</p>

<p>Add the following `set' commands in your ~/.inputrc</p>

<code>
set editing-mode vi
set keymap vi-insert</code>

<code>echo -e "\n# Vim keybindings\nset editing-mode vi\nset keymap vi-insert" >> ~/.inputrc</code>

<p>editing-mode controls the key bindings used.</p>

<p>keymap controls readline's key bindings.</p>