With the OS X firewall enabled, you can remove the "Do you want the application "python" to accept incoming network connections?" message.

<img alt="" src="/img/uploads/2014-02/os-x-accept-incoming-network-connections.png" />

Create a self-signed certificate.


* Open Keychain Access. Applications > Utilities > Keychain Access.
* Keychain Access menu > Certificate Assistant > Create a Certificate...
* Enter a Name like "My Certificate".
* Select Identity Type: Self Signed Root
* Select Certificate Type: Code Signing
* Check the Let me override defaults box
* Click Continue
* Enter a unique Serial Number
* Enter 7300 for Validity Period.
* Click Continue
* Click Continue for the rest of the dialogs


Now sign your application
```
codesign -s "My Certificate" -f $(which python)
```

In the dialog that appears, click "Allow".

Note that when using a virtual environment, you need to activate the virtual environment before running this command.