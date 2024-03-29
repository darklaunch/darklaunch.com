# Copy select files with same directory structure

Use rsync with the --files-from option to copy certain files while maintaining the same directory structure.

This is the source directory.

```bash
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
```

This is the list of files to copy. The path names are relative to the source directory. The dont-copy.txt file is not included in the list.

```bash
$ cat files_to_copy.txt
txt_files/2019/myfile.txt
1.txt
files_to_copy.txt
photos/photo001.jpg
```

```bash
$ rsync --recursive --files-from=files_to_copy.txt . /tmp/destination/
```

```bash
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
```

---

Posted Apr 29, 2019.

https://www.darklaunch.com/2019/04/29/copy-select-files-with-same-directory-structure.html