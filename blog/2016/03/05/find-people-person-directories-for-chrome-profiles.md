```sh
$ cd ~/Library/Application\ Support/Google/Chrome
$ find . -type d -iname "Profile *" -maxdepth 1 -exec php -r '$dir = ltrim("{}", "./"); echo $dir . " => "; echo json_decode(file_get_contents(getcwd() . "/" . $dir . "/Preferences"), false)->profile->name . "\n";' \;
Profile 42 => Person 1
Profile 43 => Person 2
Profile 48 => Person 6
Profile 50 => Person 8
Profile 51 => Person 9
```

kw: Google Chrome, Chromium, extensions, directory

---

Posted Mar 5, 2016.
https://www.darklaunch.com/2016/03/05/find-people-person-directories-for-chrome-profiles