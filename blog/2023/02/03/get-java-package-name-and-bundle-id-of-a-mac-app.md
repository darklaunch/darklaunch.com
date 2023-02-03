# Get Java package name and bundle id of a Mac app

Use the `osascript` command to get a package bundle id name of a Mac app:

```bash
$ osascript -e 'id of app "Hammerspoon"'
```

```
org.hammerspoon.Hammerspoon
```

Another option is to use `lsappinfo`:

```bash
$ lsappinfo info -only bundleid "Hammerspoon"
```

```
"CFBundleIdentifier"="org.hammerspoon.Hammerspoon"</samp>

The Java package name or bundle id of Hammerspoon is `org.hammerspoon.Hammerspoon`.

---

Posted Feb 3, 2023.

https://www.darklaunch.com/2023/02/03/get-java-package-name-and-bundle-id-of-a-mac-app.html