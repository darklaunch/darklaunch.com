Find unicode or non-ascii characters using grep.

```bash
$ cat myfile.txt 
Lorem
ips?m
dolor
sit
amet,
p?nderum
tritani
onstituto
in
duo.
```

Find line numbers

```bash
$ grep --line-number --perl-regexp '[^\x00-\x7F]+' myfile.txt 
2:ips?m
6:p?nderum
```

Find characters

```bash
$ grep --line-number --only-matching --perl-regexp '[^\x00-\x7F]+' myfile.txt 
2:?
6:?
```

Use grep to find unicode characters

```bash
$ grep "$(printf %b '\u2013')" myfile.txt
```

Find unicode characters in vim

```
/\%u2013
```