# Windows Disable Balloon Tips; Turn Off Traytip Notifications; regedit; registry

To disable notifications in your system tray, import the following to the registry:
```ini
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced]
"EnableBalloonTips"=dword:00000000
```
Save the above code as DisableBalloonTips.reg and open the file to import it.

---

Posted Jun 1, 2009.

https://www.darklaunch.com/2009/06/01/windows-disable-balloon-tips-turn-off-traytip-notifications-regedit-registry.html