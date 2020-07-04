Create a new file.
```
gedit ~/.wine/WORD
```
Paste this script:
```
#!/bin/sh
QUICKPARLOCATION="C:\\Program Files\\Microsoft Office\\Office12\\WINWORD.EXE"
PARAM=`winepath -w "$*"`
wine "$QUICKPARLOCATION" "$PARAM"
exit 0
```
Save the file.
Make it executable:
```
chmod +x ~/.wine/WORD
```
In Nautilus, right click on a doc document (for example, myfile.doc) and select Properties.
Select the "Open With" tab and "Add" a custom  command:
```
/home/YOURUSER/.wine/WORD
```
Now doc files will open in Microsoft Office Word.

NOTE:
For opening xls files in Excel, see
http://darklaunch.com/2009/11/06/open-microsoft-office-document-in-wine-word-excel-doc-xls-open-with