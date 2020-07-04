<p>Use rsync with the --files-from option to copy certain files while maintaining the same directory structure.</p>

<p>This is the source directory.</p>

<code name="bash">
$ tree /tmp/mydir/
/tmp/mydir/
├── 1.txt
├── files_to_copy.txt
├── photos/
│   └── photo001.jpg
└── txt_files/
    └── 2019/
        ├── dont-copy.txt
        └── myfile.txt

3 directories, 5 files
</code>

<p>This is the list of files to copy. The path names are relative to the source directory. The dont-copy.txt file is not included in the list.</p>

<code name="bash">
$ cat files_to_copy.txt
txt_files/2019/myfile.txt
1.txt
files_to_copy.txt
photos/photo001.jpg
</code>

<code name="bash">
$ rsync --recursive --files-from=files_to_copy.txt . /tmp/destination/
</code>

<code name="bash">
$ tree /tmp/destination/
/tmp/destination/
├── 1.txt
├── files_to_copy.txt
├── photos/
│   └── photo001.jpg
└── txt_files/
    └── 2019/
        └── myfile.txt

3 directories, 4 files
</code>