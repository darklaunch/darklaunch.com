# Window Manager for OS X: ShiftIt

OS X Window Manager: ShiftIt

```
$ git clone https://github.com/fikovnik/ShiftIt.git
$ cd ShiftIt/ShiftIt
$ xcodebuild -target "ShiftIt NoX11" -configuration Release
** BUILD SUCCEEDED **
$ cd build/Release
$ cp ShiftIt.app /Applications
```

https://github.com/fikovnik/ShiftIt

Configuration:

To remap Command + Ctrl + d, disable displaying a definition of the selected word in the Dictionary application. System Preferences > Keyboard > Keyboard Shortcuts tab > Services.

Run this command:

```
defaults write com.apple.symbolichotkeys AppleSymbolicHotKeys
-dict-add 70 '<dict><key>enabled</key><false/></dict>'
```

Then logout and remap Command + Ctrl + d in ShiftIt preferences.

<img alt="" src="/img/uploads/2014-02/shiftit-preferences.png" />

https://superuser.com/questions/326223/

---

Posted Feb 23, 2014.

https://www.darklaunch.com/2014/02/23/window-manager-for-os-x-shiftit.html