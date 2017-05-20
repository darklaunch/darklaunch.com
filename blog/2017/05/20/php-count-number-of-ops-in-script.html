<p>Count number of ops in a script.</p>

<p>Install php with pear.</p>

<code name="bash">
$ brew uninstall php71
$ brew install php71 --with-pear
</code>

<p>Add to bashrc file.</p>

<code name="bash">
$ vim ~/.bashrc
</code>

<code name="bash">
# Swap the PHP you use on the command line.
export PATH="$(brew --prefix homebrew/php/php71)/bin:$PATH"
</code>

<p>Ensure we are using the correct version of php. Close and reopen terminal if necessary.</p>

<code name="bash">
$ which php
/usr/local/opt/php71/bin/php
</code>

<p>Install vld.</p>

<code name="bash">
$ pecl install vld-0.14.0
</code>

<p>Create script.</p>

<code name="bash">
$ cat /tmp/script.php 
<?php
$bool = true;
if ($bool) {
    echo 'yea';
} else {
    echo 'nay';
}
</code>

<p>Run script with custom php.ini settings to view the number of ops.</p>

<code name="bash">
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
</code>

<code name="bash">
$ php \
    -dextension=vld.so \
    -dvld.active=1     \
    -dvld.dump_paths=1 \
    -dvld.execute=0    \
    -dvld.save_paths=1 \
    -dvld.verbosity=0  \
    /tmp/script.php
</code>

<code name="bash">
-dextension=vld.so # Enable vld extension.
-dvld.active=1     # Activate vld extension.
-dvld.dump_paths=1 # Dump paths.
-dvld.execute=0    # Execute script.
-dvld.save_paths=1 # Save paths. Will save paths to "/tmp/paths.dot".
-dvld.verbosity=0  # Set verbosity (0, 1, 2, 3).
</code>

<p>Install graphviz.</p>

<code name="bash">
$ brew install graphviz
</code>

<p>Render graphic. The -Tpng option renders png.</p>

<code name="bash">
$ dot -Tpng /tmp/paths.dot > /tmp/paths.png
</code>

<p>Open the paths image</p>

<code name="bash">
$ open /tmp/paths.png
</code>

<img alt="" src="/img/uploads/2017-05/paths.png" />