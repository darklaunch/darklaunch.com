# Bash run php script using multiline string

```sh
script=$(cat <<'EOF'
    $data = file_get_contents('README.md');
    var_dump($data);
EOF
)
php --run "${script}"
```

---

Posted Nov 9, 2022.

https://www.darklaunch.com/2022/11/09/bash-run-php-script-using-multiline-string.html