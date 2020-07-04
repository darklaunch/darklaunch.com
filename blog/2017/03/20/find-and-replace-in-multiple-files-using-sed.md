Replace string in multiple files using the find and sed commands.

```bash
find="hello"
replace="hi"
find ./ -type f -exec sed -i -e "s/${find}/${replace}/g" {} \;
```

Replace string in a file using the sed command.

```bash
find="hello"
replace="hi"
sed -i -e "s/${find}/${replace}/g" myfile.txt
```

Run several commands on files found by using the exec option multiple times.

```
find . -type f -name "*.txt" -exec file {} \; -exec cat {} \; -exec sed -i -e "s/before/after/g" {} \; -exec cat {} \;
```

Note: Possible error "sed: can't read : No such file or directory" or "invalid command code". Fix by using an empty extension for the -i parameter. Also fix by adding or removing a space between the parameter flag and the corresponding parameter value.

```bash
sed -i 's/before/after/' myfile.txt
sed -i '' -e 's/before/after/' myfile.txt
sed -i'' -e's/before/after/' myfile.txt
```