Grep stderr by redirecting stderr to stdout.

```bash
my_command 2>&1 | grep --color my_keyword
```

Grep only stderr by redirecting stderr to stdout and redirecting stdout to /dev/null.

```bash
my_command 2>&1 > /dev/null | grep --color my_keyword
```

<img alt="" src="/img/uploads/2015-01/php-grep-stderr-stdout.png" />

```sh
php -r 'fwrite(STDOUT, "stdout\n");fwrite(STDERR, "stderr\n");' | grep --color std
php -r 'fwrite(STDOUT, "stdout\n");fwrite(STDERR, "stderr\n");' 2>&1 | grep --color std
php -r 'fwrite(STDOUT, "stdout\n");fwrite(STDERR, "stderr\n");' 2>&1 > /dev/null | grep --color std
```

---

Posted Jan 2, 2015.

https://www.darklaunch.com/2015/01/02/bash-grep-stderr-and-stdout.html