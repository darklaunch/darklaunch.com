<p>Open multiple files in python using file context managers.</p>

<code name="python">
import csv


with open('in.csv', 'r') as fr, open('out.csv', 'w') as fw:
    reader = csv.reader(fr)
    writer = csv.writer(fw)

    for i, row in enumerate(reader):
        row.insert(0, i)
        writer.writerow(row)
</code>