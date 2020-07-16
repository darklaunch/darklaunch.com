Geany snippets configuration file is located in:
```
/usr/share/geany/snippets.conf
```
Edit the file:
```
sudo geany /usr/share/geany/snippets.conf
```
Save and restart geany. Now type the word if and the tab key. This will autocomplete an if statement.
```ini
# from http://citizen.ovh.org/stuff/snippets.conf
# Geany's snippets configuration file
# use \n or %newline% for a new line (it will be replaced by the used EOL char(s) - LF, CR/LF, CR)
# use \t ot %ws% for an indentation step, if using only spaces for indentation only spaces will be used
# use \s to force whitespace at beginning or end of a value ('key= value' won't work, use 'key=\svalue')
# use %cursor% to define where the cursor should be placed after completion
# use %key% for all keys defined in the [Special] section
# you can define a section for each supported filetype to overwrite default settings, the section
# name must match exactly the internal filetype name, run 'geany --ft-names' for a full list

# filetype names:
# C, C++, D, Java, Pascal, ASM, Fortran, CAML, Haskell, VHDL, Perl, PHP, Javascript, Python, Ruby,
# Tcl, Lua, Ferite, Sh, Make, O-Matrix, XML, Docbook, HTML, CSS, SQL, LaTeX, Diff, Conf, None

# Default is used for all filetypes and keys can be overwritten by [filetype] sections
[Default]
if=if (%cursor%)%brace_open%\n%brace_close%
else=else%brace_open%%cursor%\n%brace_close%
for=for (i = 0; i < %cursor%; i++)%brace_open%\n%brace_close%
while=while (%cursor%)%brace_open%\n%brace_close%
do=do%brace_open%%cursor%\n%brace_close% while ()
switch=switch (%cursor%)%brace_open%case : break;\n%ws%default: \n%brace_close%
try=try%block_cursor%catch ()%block%

# special keys to be used in other snippets, cannot be used "standalone"
# can be used by %key%, e.g. %brace_open%
# nesting of special keys is not supported (e.g. brace_open=\n{\n%brace_close% won't work)
# key "wordchars" is very special, it defines the word delimiting characters when looking for
# a word to auto complete, leave commented to use the default wordchars
[Special]
brace_open=\n{\n\t
brace_close=}\n
block=\n{\n\t\n}\n
block_cursor=\n{\n\t%cursor%\n}\n
#wordchars=_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789

[C++]
for=for (int i = 0; i < %cursor%; i++)%brace_open%\n%brace_close%

[Java]
for=for (int i = 0; i < %cursor%; i++)%brace_open%\n%brace_close%

[PHP]
# Little php snippets written by Atanas Beloborodov <nasko@cod3r.org>
#Some php5 object`s usefull snippets
class=class %cursor% \n{\n\tpublic function __construct()\n\t{\t\n\n\t}\n\n\tpublic function __destruct()\n\t{\t\n\n\t}\n}
interface=interface %cursor% %block%
static=public static function %cursor%() %block%
public=public function %cursor%()%block%
protected=protected function %cursor%()%block%
private=private function %cursor%()%block%
#Control structures :
for=for ($i = 0; $i < %cursor%; $i++ %block%
while=while (%cursor%) %block%
if=if (%cursor%) %block%
switch=switch (%cursor%) {\n\tcase '';\n\n\tbreak;\n\n\tdefault :\n\n\tbreak;\n}\n
else=if (%cursor%) %block%else %block%
elseif=if (%cursor%) {\n\t\n}\nelseif () {\n\t\n}\nelse {\n\t\n}\n
do=do %block%while (%cursor%);
foreach=foreach (%cursor%) %block%
# Include methods
# Note : require and include is not functions ! Not required braces () 
req=require "%cursor%";
reqo=require_once "%cursor%";
inc=include "%cursor%";
inco=include_once "%cursor%";
# Others :
function=function %cursor%() %block%
def=define ('%cursor%','');
throw=throw new Exception ('%cursor%');e%

[Python]
for=for i in xrange(%cursor%):\n\t

[Ferite]
iferr=iferr%block_cursor%fix%block%
monitor=monitor%block_cursor%handle%block%

[HTML]
# by Tomasz Karbownicki <tomasz@karbownicki.com>
# top
html=<html>\n\t%cursor%\n</html>
head=<head>\n\t%cursor%\n</head>
java=<script type="text/javascript">\n\t%cursor%\n</script>
java2=<script type="text/javascript" src="%cursor%"></script>
css=<style type="text/css">\n\t%cursor%\n</style>
css2=<link rel="stylesheet" type="text/css" href="%cursor%" />
rss=<link rel="alternate" type="application/rss+xml" title="%cursor%" href="" />
title=<title>%cursor%</title>
utf=<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
body=<body>\n\t%cursor%\n</body>
# table
table=<table>\n\t<thead>\n\t\t<tr>\n\t\t\t<th>%cursor%</th>\n\t\t</tr>\n\t</thead>\n\t<tbody>\n\t\t<tr>\n\t\t\t<td></td>\n\t\t</tr>\n\t</tbody>\n</table>
td=<td>%cursor%</td>
tr=<tr>%cursor%</tr>
th=<th>%cursor%</th>
caption=<caption>%cursor%</caption>
# form
form=<form action="%cursor%" method="post">\n\n\t<input type="submit" value="Zapisz" />\n</form>
label=<label for="%cursor%"></label>
input=<input type="text" name="%cursor%" value="" id="" />
pass=<input type="password" name="%cursor%" id="" />
textarea=<textarea name="%cursor%" cols="50" rows="10" id="" ></textarea>
select=<select name="%cursor%" id="">\n\t<option value=""></option>\n</select>
radio=<input type="radio" name="%cursor%" value="" />
checkbox=<input type="checkbox" name="%cursor%" value="" />
# list
ul=<ul class="%cursor%">\n\t<li></li>\n
ol=<ol class="%cursor%">\n\t<li></li>\n
li=<li>%cursor%
# inline
span=<span class="%cursor%"></span>
em=<em>%cursor%</em>
cite=<cite>%cursor%</cite>
strong=<strong>%cursor%</strong>
img=<img src="%cursor%" alt="" />
anch=<a name="%cursor%"></a>
thumb=<a href="%cursor%"><img src="" /></a>
# block
div=<div class="%cursor%"></div>
h1=<h1>%cursor%</h1>
h2=<h2>%cursor%</h2>
h3=<h3>%cursor%
h4=<h4>%cursor%</h4>
h5=<h5>%cursor%</h5>
h6=<h6>%cursor%</h6>
p=%cursor%
pre=<pre>\n%cursor%\n</pre>
code=```
\n%cursor%\n
```
quote=> \n\t\n\t\t%cursor%\n\t\n
# other
cmt=<!--\n\t%cursor%\n-->
br=&lt;br/>
hr=&lt;hr/>
1s=&nbsp;
3s=&nbsp;&nbsp;&nbsp;
7s=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
# Django templates
if={% if %cursor% %}\n\t\n{% endif %}
for={% for sth in %cursor% %}\n\t\n{% endfor %}
# Django variable
dv={{ %cursor% }}
# Django block
db={% %cursor% %}
```