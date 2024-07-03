# Bash get unicode character from encoded char

Use hexdump to lookup the 6-digit unicode sequence. Examples for bash and python are given.

```bash
$ echo -n ✓ | hexdump
0000000 e2 9c 93
0000003
```

To print the character, escape the 6-digit / 3 byte unicode sequence. Use -e with echo to interpret the escaped characters.

```bash
$ echo -e "\xE2\x9c\x93"
✓
```

Example with color and subscripts on the command line:

```bash
$ echo -e 'O\xe2\x82\x82 Sensor: \x1b[1;32m\xE2\x9c\x93\x1b[0m'
O₂ Sensor: ✓
```

<img alt="" src="/img/uploads/2013-04/bash-echo-unicode-characters.png" />

To print the unicode character in python, do the following:

```python
>>> print "\xE2\x9c\x93"
✓
```

List of colors for bash prompt:

```sh
# Reset
Color_Off='\e[0m'       # Text Reset

# Regular Colors
Black='\e[0;30m'        # Black
Red='\e[0;31m'          # Red
Green='\e[0;32m'        # Green
Yellow='\e[0;33m'       # Yellow
Blue='\e[0;34m'         # Blue
Purple='\e[0;35m'       # Purple
Cyan='\e[0;36m'         # Cyan
White='\e[0;37m'        # White

# Bold
BBlack='\e[1;30m'       # Black
BRed='\e[1;31m'         # Red
BGreen='\e[1;32m'       # Green
BYellow='\e[1;33m'      # Yellow
BBlue='\e[1;34m'        # Blue
BPurple='\e[1;35m'      # Purple
BCyan='\e[1;36m'        # Cyan
BWhite='\e[1;37m'       # White

# Underline
UBlack='\e[4;30m'       # Black
URed='\e[4;31m'         # Red
UGreen='\e[4;32m'       # Green
UYellow='\e[4;33m'      # Yellow
UBlue='\e[4;34m'        # Blue
UPurple='\e[4;35m'      # Purple
UCyan='\e[4;36m'        # Cyan
UWhite='\e[4;37m'       # White

# Background
On_Black='\e[40m'       # Black
On_Red='\e[41m'         # Red
On_Green='\e[42m'       # Green
On_Yellow='\e[43m'      # Yellow
On_Blue='\e[44m'        # Blue
On_Purple='\e[45m'      # Purple
On_Cyan='\e[46m'        # Cyan
On_White='\e[47m'       # White

# High Intensity
IBlack='\e[0;90m'       # Black
IRed='\e[0;91m'         # Red
IGreen='\e[0;92m'       # Green
IYellow='\e[0;93m'      # Yellow
IBlue='\e[0;94m'        # Blue
IPurple='\e[0;95m'      # Purple
ICyan='\e[0;96m'        # Cyan
IWhite='\e[0;97m'       # White

# Bold High Intensity
BIBlack='\e[1;90m'      # Black
BIRed='\e[1;91m'        # Red
BIGreen='\e[1;92m'      # Green
BIYellow='\e[1;93m'     # Yellow
BIBlue='\e[1;94m'       # Blue
BIPurple='\e[1;95m'     # Purple
BICyan='\e[1;96m'       # Cyan
BIWhite='\e[1;97m'      # White

# High Intensity backgrounds
On_IBlack='\e[0;100m'   # Black
On_IRed='\e[0;101m'     # Red
On_IGreen='\e[0;102m'   # Green
On_IYellow='\e[0;103m'  # Yellow
On_IBlue='\e[0;104m'    # Blue
On_IPurple='\e[0;105m'  # Purple
On_ICyan='\e[0;106m'    # Cyan
On_IWhite='\e[0;107m'   # White
```

---

Posted Apr 25, 2013.

https://www.darklaunch.com/2013/04/25/bash-get-unicode-character-from-encoded-char.html

---

5 comments

<ol><li><div>

anonymous &ndash; Oct 21, 2013<div>

more characters:

check
$ echo -n âœ”|hexdump
0000000 e2 9c 94
0000003

x
$ echo -n âœ–|hexdump
0000000 e2 9c 96
0000003

arrow
$ echo -n âžœ|hexdump
0000000 e2 9e 9c
0000003

</div></div></li><li><div>

anonymous &ndash; Feb 23, 2014<div>

These color codes are incomplete for some reason beyond my knowledge and fail sometimes when a line is too long, overwriting the prompt's first line content and producing weird behaviours because prompt won't start a new line or even go one line up.

In order for these color codes to work (at least in ubuntu), you need to replace
\e with [\033 and add at the end of every code \].

So instead of
Red='\e[0;31m'          # Red
You should type
Red='\[\033[0;31m\]'          # Red

</div></div></li><li><div>

anonymous &ndash; Nov 11, 2014<div>

It's also possible to get the unicode sequence on the command line using python:

$ echo -n "âœ“" | python -c 'import sys; print [sys.stdin.read()]'
['\xe2\x9c\x93']

</div></div></li><li><div>

anonymous &ndash; Jul 29, 2016<div>

$ echo -n "â€" | python -c 'import sys; print [sys.stdin.read()]'
['\xe2\x80\x9d']

</div></div></li><li><div>

anonymous &ndash; Aug 25, 2023<div>

see also the command `xxd'.

```
$ xxd -g1 myfile.gz
```

</div></div></li></ol>