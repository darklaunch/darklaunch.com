To close Terminal after a script completes you will need to change it in the profile preference.

Open Terminal.
Right-click in the window and select Profile > Profile Preferences.
Open the Title and Command tab.
For "When command exists:" select "Exit the terminal".

NOTE:
myscript.py required user input. So I added  a Keyboard Shortcut with the "Command" of:
```
gnome-terminal --command=/path/to/myscript.py
```
The shortcut opens a terminal window for the input. The scripts then runs and the Terminal window closes after the script completes.

---


Posted Oct 14, 2009.
https://www.darklaunch.com/2009/10/14/close-terminal-after-script-completes-command-exits.html