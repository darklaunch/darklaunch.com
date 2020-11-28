Read many files as a single file using a generator function.

```python
import csv
import pprint

def read_multiple_files_as_one():
  with open('first.csv', 'r') as f_in:
    reader = csv.DictReader(f_in)
    for i, row in enumerate(reader):
      yield i, row

  with open('second.csv', 'r') as f_in:
    reader = csv.DictReader(f_in)
    for i, row in enumerate(reader):
      yield i, row

for _, row in read_multiple_files_as_one():
  pprint.pprint(row)
```

```bash
$ cat first.csv
col1,col2
a,b

$ cat second.csv
col1,col2
c,d

$ python read_files.py
```

```
{'col1': 'a', 'col2': 'b'}
{'col1': 'c', 'col2': 'd'}
```

---

Posted Oct 11, 2020.

https://www.darklaunch.com/2020/10/11/python-read-multiple-files-as-a-single-file.html