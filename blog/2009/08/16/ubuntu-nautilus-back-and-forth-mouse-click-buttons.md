Navigate back and forward in Nautilus using the mouse back/forward buttons:

Run in terminal:
```
sudo apt-get install xvkbd xbindkeys x11-utils
```

Find the mouse keys:
```
xev | grep ', button'
```
Click in the window to see the mouse codes. Example:
```
    state 0x10, button 8, same_screen YES
    state 0x10, button 8, same_screen YES
    state 0x10, button 9, same_screen YES
    state 0x10, button 9, same_screen YES
```
8 for left thumb click, 9 for right thumb click.

Edit the key bindings. Terminal:
```
gedit ~/.xbindkeysrc
```
```
"/usr/bin/xvkbd -xsendevent -text "\[Alt_L]\[Left]""
  m:0x0 + b:8
"/usr/bin/xvkbd -xsendevent -text "\[Alt_L]\[Right]""
  m:0x0 + b:9
```

Run xbindkeys in terminal:
```
xbindkeys
```

Now clicking the back and forth mouse keys will navigate back and forth in Nautilus.

---


Posted Aug 16, 2009.
https://www.darklaunch.com/2009/08/16/ubuntu-nautilus-back-and-forth-mouse-click-buttons.html