Count number of ops in a script.

Install php with pear.

```bash
$ brew uninstall php71
$ brew install php71 --with-pear
```

Add to bashrc file.

```bash
$ vim ~/.bashrc
```

```bash
# Swap the PHP you use on the command line.
export PATH="$(brew --prefix homebrew/php/php71)/bin:$PATH"
```

Ensure we are using the correct version of php. Close and reopen terminal if necessary.

```bash
$ which php
/usr/local/opt/php71/bin/php
```

Install vld.

```bash
$ pecl install vld-0.14.0
```

Create script.

```bash
$ cat /tmp/script.php 
<?php
$bool = true;
if ($bool) {
    echo 'yea';
} else {
    echo 'nay';
}
```

Run script with custom php.ini settings to view the number of ops.

```bash
$ php -dextension=vld.so -dvld.active=1 -dvld.dump_paths=1 -dvld.execute=0 -dvld.save_paths=1 -dvld.verbosity=0 /tmp/script.php
filename:       /private/tmp/script.php
function name:  (null)
number of ops:  6
compiled vars:  !0 = $bool
line     #* E I O op                           fetch          ext  return  operands
-------------------------------------------------------------------------------------
   2     0  E >   ASSIGN                                                   !0, <true>
   3     1      > JMPZ                                                     !0, ->4
   4     2    >   ECHO                                                     'yea'
         3      > JMP                                                      ->5
   6     4    >   ECHO                                                     'nay'
   8     5    > > RETURN                                                   1

branch: #  0; line:     2-    3; sop:     0; eop:     1; out1:   2; out2:   4
branch: #  2; line:     4-    4; sop:     2; eop:     3; out1:   5
branch: #  4; line:     6-    8; sop:     4; eop:     4; out1:   5
branch: #  5; line:     8-    8; sop:     5; eop:     5; out1:  -2
path #1: 0, 2, 5, 
path #2: 0, 4, 5,
```

```bash
$ php \
    -dextension=vld.so \
    -dvld.active=1     \
    -dvld.dump_paths=1 \
    -dvld.execute=0    \
    -dvld.save_paths=1 \
    -dvld.verbosity=0  \
    /tmp/script.php
```

```bash
-dextension=vld.so # Enable vld extension.
-dvld.active=1     # Activate vld extension.
-dvld.dump_paths=1 # Dump paths.
-dvld.execute=0    # Execute script.
-dvld.save_paths=1 # Save paths. Will save paths to "/tmp/paths.dot".
-dvld.verbosity=0  # Set verbosity (0, 1, 2, 3).
```

Install graphviz.

```bash
$ brew install graphviz
```

Render graphic. The -Tpng option renders png.

```bash
$ dot -Tpng /tmp/paths.dot > /tmp/paths.png
```

Open the paths image

```bash
$ open /tmp/paths.png
```

<img alt="" src="/img/uploads/2017-05/paths.png" />