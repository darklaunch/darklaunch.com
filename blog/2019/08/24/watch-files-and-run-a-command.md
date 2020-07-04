Watch the current directory for changes and run a command using watchman.

Install watchman:
```bash
$ brew install watchman
```
Use watchman-make to automatically run a command when any files matching the pattern ("-p") change:
```bash
$ watchman-make -p "**" --run "/usr/bin/do_thing --verbose"
```