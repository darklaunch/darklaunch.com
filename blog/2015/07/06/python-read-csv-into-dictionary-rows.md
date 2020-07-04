<p>Read a csv with headers in python into dictionary rows mapping to the headers.</p>

<code>
first,last,sex
Liberia,Mariana,female
Eligius,Prosperus,male
Florina,Xenia,female</code>

<p>Use csv.DictReader to read each row into a dictionary.</p>

<code name="python">
import csv

with open('data.csv') as f:
    reader = csv.DictReader(f)
    print('headers: {}'.format(reader.fieldnames))
    for row in reader:
        print(row)
</code>

<code name="sh">
$ python read_csv.py 
headers found: ['first', 'last', 'sex']
{'sex': 'female', 'last': 'Mariana', 'first': 'Liberia'}
{'sex': 'male', 'last': 'Prosperus', 'first': 'Eligius'}
{'sex': 'female', 'last': 'Xenia', 'first': 'Florina'}
</code>

<p>Alternatively, use csv.reader to read the rows.</p>

<code name="python">
import csv

with open('data.csv') as f:
    reader = csv.reader(f)
    headers = reader.next()
    print('headers found: {}'.format(headers))
    for row_list in reader:
        row_dict = dict(zip(headers, row_list))
        print(row_dict)
</code>

<p>You can also read the next line by doing either reader.next() or next(reader):</p>
<code name="python">
headers = reader.next()
headers = next(reader)
</code>