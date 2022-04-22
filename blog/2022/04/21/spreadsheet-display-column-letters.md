# Spreadsheet display column letters

Display spreadsheet column letters using the following formula:

```
=REGEXREPLACE(ADDRESS(ROW(), COLUMN(), 4), "[[:^alpha:]]", "")
```

<img alt="" src="/img/uploads/2022-04/spreadsheet-column-letters.png" />

---

Posted Apr 21, 2022.

https://www.darklaunch.com/2022/04/21/spreadsheet-display-column-letters.html