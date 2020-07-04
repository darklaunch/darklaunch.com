To disable notifications in your system tray, import the following to the registry:
<code name="ini">
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced]
"EnableBalloonTips"=dword:00000000
</code>
Save the above code as DisableBalloonTips.reg and open the file to import it.