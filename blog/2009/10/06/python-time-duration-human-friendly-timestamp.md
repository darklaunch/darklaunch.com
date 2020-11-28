```python
def duration_human(seconds):
    seconds = long(round(seconds))
    minutes, seconds = divmod(seconds, 60)
    hours, minutes = divmod(minutes, 60)
    days, hours = divmod(hours, 24)
    years, days = divmod(days, 365.242199)

    minutes = long(minutes)
    hours = long(hours)
    days = long(days)
    years = long(years)

    duration = []
    if years > 0:
        duration.append('%d year' % years + 's'*(years != 1))
    else:
        if days > 0:
            duration.append('%d day' % days + 's'*(days != 1))
        if hours > 0:
            duration.append('%d hour' % hours + 's'*(hours != 1))
        if minutes > 0:
            duration.append('%d minute' % minutes + 's'*(minutes != 1))
        if seconds > 0:
            duration.append('%d second' % seconds + 's'*(seconds != 1))
    return ' '.join(duration)
```

Example:
```python
seconds = [
    1,
    2,
    3600,
    7201,
    49020,
    86400,
    100000,
    172800,
    300000,
    31697026,
    63200000,
    95000000,
    999999999,
]
for s in seconds:
    print('{} => {}'.format(str(s).rjust(10, ' '), duration_human(s)))
```

Example Output:

```
.        1 => 1 second
         2 => 2 seconds
      3600 => 1 hour
      7201 => 2 hours 1 second
     49020 => 13 hours 37 minutes
     86400 => 1 day
    100000 => 1 day 3 hours 46 minutes 40 seconds
    172800 => 2 days
    300000 => 3 days 11 hours 20 minutes
  31697026 => 1 year
  63200000 => 2 years
  95000000 => 3 years
 999999999 => 31 years
```

Example 2:

```python
import time

start = time.time()

time.sleep(1)

end = time.time()
elapsed = end - start
print('{} has passed'.format(duration_human(elapsed)))
```

Example 2 Output:

```
1 second has passed
```

---

Posted Oct 6, 2009.

https://www.darklaunch.com/2009/10/06/python-time-duration-human-friendly-timestamp.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Nov 29, 2013
            <div>
good!!
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 19, 2014
            <div>
import datetime
import time

start = datetime.datetime.now()

time.sleep(2)

elapsed = datetime.datetime.now() - start
print elapsed
            </div>
        </div>
    </li>
</ol>
