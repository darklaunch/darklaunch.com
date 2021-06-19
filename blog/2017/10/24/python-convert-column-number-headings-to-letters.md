# Python convert column number headings to letters

```python
def col_num_to_char(col):
    char = ''
    div = col
    while div:
        div, mod = divmod(div - 1, 26)
        char = chr(mod + 65) + char
    return char
```
```python
>>> print(col_num_to_char(1))
A
>>> print(col_num_to_char(2))
B
>>> print(col_num_to_char(3))
C
>>> print(col_num_to_char(24))
X
>>> print(col_num_to_char(25))
Y
>>> print(col_num_to_char(26))
Z
>>> print(col_num_to_char(27))
AA
>>>
```
kw: Microsoft Excel, Google Sheets, A1, R1C1, spreadsheet, column, row

---

Posted Oct 24, 2017.

https://www.darklaunch.com/2017/10/24/python-convert-column-number-headings-to-letters.html