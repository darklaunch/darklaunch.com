To remap Caps Lock to F12, go to Ubuntu > Startup Applications > Add > enter the command:

```
xmodmap -e "keycode 66 = F12"
```

This will remap caps lock to f12 at every startup.
Also, ensure that the caps lock is does not actually type in all caps:

```
$ sudo apt-get install -y gnome-tweak-tool
```

Tweaks > Typing > Caps Lock key behavior :: Caps Lock is disabled