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

---

Posted Nov 6, 2009.

https://www.darklaunch.com/2009/11/06/open-microsoft-office-document-in-wine-word-excel-doc-xls-open-with.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Nov 1, 2012
            <div>
                <p>Very usefull. Thanks!</p>
            </div>
        </div>
    </li>
</ol>
