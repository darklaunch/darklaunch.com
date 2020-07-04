One solution to add files recursively with svn is to use the --force option. An example of this is:
```
svn add * --force
```
There is another solution. This is what I came up with:
```
php -r '$files = array(); foreach (simplexml_load_string($argv["1"])->target->entry as $entry) { if ($entry->{"wc-status"}->attributes()->item == "unversioned") { $files[] = chr(34) . (string)$entry->attributes()->path . chr(34); }; } echo implode(" ", $files) . "\n"; ' "$(svn status --xml)" | xargs svn add
```
<h4>How this Works</h4>
1. svn status is passed/piped to php via xml.
2. php reads the xml and looks for anything that is "unversioned" and echos the filename
3. xargs picks up the echoed filenames and executes svn add to each of the files

And as an alias for recursively svn adding unversioned files:
```sh
# svn add unversioned files
alias sau="php -r '\$files = array(); foreach (simplexml_load_string(\$argv[\"1\"])->target->entry as \$entry) { if (\$entry->{\"wc-status\"}->attributes()->item == \"unversioned\") { \$files[] = chr(34) . (string)\$entry->attributes()->path . chr(34); }; } echo implode(\" \", \$files) . \"\n\"; ' \"\$(svn status --xml)\" | xargs svn add"
```