Watch the current directory for changes and run a command using watchman.

Install watchman:

```bash
$ brew install watchman
```

Use watchman-make to automatically run a command when any files matching the pattern ("-p") change:

```bash
$ watchman-make -p "**" --run "/usr/bin/do_thing --verbose"
```

---

Posted Aug 24, 2019.

https://www.darklaunch.com/2019/08/24/watch-files-and-run-a-command.html