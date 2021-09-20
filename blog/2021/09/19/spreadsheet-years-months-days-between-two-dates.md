# Spreadsheet display years, months, and days between two dates

Display the number of years, months, and days between two dates in a spreadsheet.

<img alt="" src="/img/uploads/2021-09/spreadsheet-year-month-day-difference.png" />

```
=JOIN(
    ", ",
    FILTER(
        {
            DATEDIF(StartDate, EndDate, "y") & " years",
            DATEDIF(StartDate, EndDate, "ym") & " months",
            DATEDIF(StartDate, EndDate, "md") & " days"
        },
        {
            DATEDIF(StartDate, EndDate, "y"),
            DATEDIF(StartDate, EndDate, "ym"),
            DATEDIF(StartDate, EndDate, "md")
        }
    )
)
```

Replace `StartDate` and `EndDate` with spreadsheet cell references. Now the number of years, months, and days between the two dates will be displayed.

When there are 0 years, 0 months, or 0 days, those values will be filtered out and not displayed.

---

Posted Sep 19, 2021.

https://www.darklaunch.com/2021/09/19/spreadsheet-years-months-days-between-two-dates.html