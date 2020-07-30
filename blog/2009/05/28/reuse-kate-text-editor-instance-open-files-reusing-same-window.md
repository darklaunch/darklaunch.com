To tell Kate Advanced Text Editor to re-use any already open windows, do the following:
```
1. Right click on the file to open with Kate and select Properties > Open With tab.
2. In the new window, click the Add button.
3. At the bottom under "Use a custom command" type: kate -u %U and click Add.
4. Select the newly added open with application and Close the window.
```
Now opening multiple files associated with Kate will re-use the existing window.
The -u tells Take to open files in the same Kate instance.

NOTE: or use '/usr/bin/kate' -u %U

---

Posted May 28, 2009.
https://www.darklaunch.com/2009/05/28/reuse-kate-text-editor-instance-open-files-reusing-same-window