Quote or escape the limit string at the beginning of the here document (heredoc) to disable parameter substitution (variables).

In the following example, escape EOF as \EOF. You can also put the limit string in quotes: "EOF".

<img alt="" src="/img/uploads/2015-07/bash-run-php-script.png" />

```sh
php <<\EOF
<?php
echo rand() . "\n";
EOF
```

```sh
php <<"EOF"
<?php
echo rand() . "\n";
EOF
```

---

Posted Jul 17, 2015.

https://www.darklaunch.com/2015/07/17/bash-run-php-script-disable-variables-inside-heredoc-multi-line-comment.html