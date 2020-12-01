Read a csv with headers in python into dictionary rows mapping to the headers.

```
first,last,sex
Liberia,Mariana,female
Eligius,Prosperus,male
Florina,Xenia,female
```

Use `csv.DictReader` to read each row into a dictionary.

```python
import csv

with open('data.csv') as f:
    reader = csv.DictReader(f)
    print('headers: {}'.format(reader.fieldnames))
    for row in reader:
        print(row)
```

```sh
$ python read_csv.py 
headers found: ['first', 'last', 'sex']
{'sex': 'female', 'last': 'Mariana', 'first': 'Liberia'}
{'sex': 'male', 'last': 'Prosperus', 'first': 'Eligius'}
{'sex': 'female', 'last': 'Xenia', 'first': 'Florina'}
```

Alternatively, use `csv.reader` to read the rows.

```python
import csv

with open('data.csv') as f:
    reader = csv.reader(f)
    headers = reader.next()
    print('headers found: {}'.format(headers))
    for row_list in reader:
        row_dict = dict(zip(headers, row_list))
        print(row_dict)
```

You can also read the next line by doing either `reader.next()` or `next(reader)`:
```python
headers = reader.next()
headers = next(reader)
```

---

Posted Jul 6, 2015.

https://www.darklaunch.com/2015/07/06/python-read-csv-into-dictionary-rows.html