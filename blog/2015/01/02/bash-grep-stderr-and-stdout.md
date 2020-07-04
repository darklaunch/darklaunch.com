Grep stderr by redirecting stderr to stdout.

```bashmy_command 2>&1 | grep --color my_keyword```

Grep only stderr by redirecting stderr to stdout and redirecting stdout to /dev/null.

```bashmy_command 2>&1 > /dev/null | grep --color my_keyword```

<a href="/img/uploads/2015-01/php-grep-stderr-stdout.png"><img alt="" src="/img/uploads/2015-01/php-grep-stderr-stdout.png" /></a>

```sh
php -r 'fwrite(STDOUT, "stdout\n");fwrite(STDERR, "stderr\n");' | grep --color std
php -r 'fwrite(STDOUT, "stdout\n");fwrite(STDERR, "stderr\n");' 2>&1 | grep --color std
php -r 'fwrite(STDOUT, "stdout\n");fwrite(STDERR, "stderr\n");' 2>&1 > /dev/null | grep --color std
```