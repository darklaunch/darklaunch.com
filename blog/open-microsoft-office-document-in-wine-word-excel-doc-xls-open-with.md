Create a new file.
```
gedit ~/.wine/EXCEL
```
Paste this script:
```
#!/bin/sh
QUICKPARLOCATION="C:\\Program Files\\Microsoft Office\\Office12\\EXCEL.EXE"
PARAM=`winepath -w "$*"`
wine "$QUICKPARLOCATION" "$PARAM"
exit 0
```
Save the file.
Make it executable:
```
chmod +x ~/.wine/EXCEL
```
In Nautilus, right click on an xls document (for example, myfile.xls) and select Properties.
Select the "Open With" tab and "Add" a custom  command:
```
/home/YOURUSER/.wine/EXCEL
```
Now xls files will open in Microsoft Office Excel.

NOTE:
For opening doc files in Word, see
http://darklaunch.com/2009/12/01/open-microsoft-office-document-in-wine-word-microsoft-doc-files-open-with