# Find the last value in a spreadsheet column

Here is a formula to find the last value in a column of a spreadsheet.

```
=INDEX(
    TRANSPOSE(FILTER(B:B, NOT(ISBLANK(B:B)))),
    1,
    COUNTA(B:B)
)
```

<img alt="" src="/img/uploads/2022-03/spreadsheet-last-value-in-column.png" />

---

Posted Mar 19, 2022.

https://www.darklaunch.com/2022/03/19/find-the-last-value-in-a-spreadsheet-column.html