# Spreadsheet insert rows from another sheet using Google Sheets

Insert a range of rows from another sheet in Google Sheets.

Use `ARRAYFORMULA()` instead of `IMPORTRANGE()` when referencing the a sheet in the same spreadsheet as `ARRAYFORMULA()` is faster.

Here's how to pass an array (using brackets) to reference multiple ranges:

```
=ARRAYFORMULA({MySheet!B3:B, MySheet!D3:D})
```

If you just need to reference a basic range, use something like this:

```
=ARRAYFORMULA(MySheet!B3:B)
```

Slower using `IMPORTRANGE()`, but needed if referencing a sheet from a different spreadsheet:

```
=IMPORTRANGE("https://docs.google.com/spreadsheets/d/01234567890/", "MySheet!B3:B")
```

<img alt="" src="/img/uploads/2022-06/spreadsheet-insert-rows-another-sheet-arrayformula.png" />

---

Posted Jun 25, 2022.

https://www.darklaunch.com/2022/06/25/spreadsheet-insert-rows-from-another-sheet-google-sheets.html