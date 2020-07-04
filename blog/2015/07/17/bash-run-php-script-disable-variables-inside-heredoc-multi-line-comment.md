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