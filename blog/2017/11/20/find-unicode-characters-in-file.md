Find unicode or non-ascii characters using grep.
```bash
$ cat myfile.txt 
Lorem
ipsūm
dolor
sit
amet,
pōnderum
tritani
onstituto
in
duo.
```
Find line numbers
```bash
$ grep --line-number --perl-regexp '[^\x00-\x7F]+' myfile.txt 
2:ipsūm
6:pōnderum
```
Find characters
```bash
$ grep --line-number --only-matching --perl-regexp '[^\x00-\x7F]+' myfile.txt 
2:ū
6:ō
```
Use grep to find unicode characters
```bash
$ grep "$(printf %b '\u2013')" myfile.txt
```
Find unicode characters in vim
```
/\%u2013
```