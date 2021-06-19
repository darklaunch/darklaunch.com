# Google Calendar last day of month repeat

To create a last day of month event in Google Calendar, create a new file "myevent.ics" with the contents:

```
BEGIN:VCALENDAR
CALSCALE:GREGORIAN
VERSION:2.0
BEGIN:VEVENT
RRULE:FREQ=MONTHLY;INTERVAL=1;BYSETPOS=-1;BYDAY=SU,MO,TU,WE,TH,FR,SA
SUMMARY:Title here.
DTSTART;VALUE=DATE:20160331
SEQUENCE:0
DESCRIPTION:Description here.
END:VEVENT
END:VCALENDAR
```

Update "SUMMARY:Title here.", "DESCRIPTION:Description here.", and "DTSTART;VALUE=DATE:20160331" as needed.

The recurrence rule (RRULE) field with BYSETPOS=-1 causes the event to be the first day of the month less 1 day.

Import into Google Calendar:

<img alt="" src="/img/uploads/2016-06/google-calendar-import-calendar.png" />
<img alt="" src="/img/uploads/2016-06/google-calendar-import.png" />
<img alt="" src="/img/uploads/2016-06/google-calendar-event-repeat.png" />

Google Calendar warning: "This event has a recurrence rule that cannot be edited in Google Calendar".

---

Posted Jun 13, 2016.

https://www.darklaunch.com/2016/06/13/google-calendar-last-day-of-month-repeat.html

---

7 comments

<ol><li><div>

anonymous &ndash; Oct 29, 2016<div>

works great thank you!

</div></div></li><li><div>

anonymous &ndash; Feb 1, 2017<div>

Perfect, thanks!

</div></div></li><li><div>

anonymous &ndash; Oct 25, 2017<div>

THANK YOU!!!

</div></div></li><li><div>

anonymous &ndash; Feb 19, 2018<div>

Works dude. Thanks a bunch. Please add litecoin for tips ;)

</div></div></li><li><div>

anonymous &ndash; May 20, 2018<div>

Thank you for helping overcome a major nuisance of Google Calendar! Works wonderfully.

</div></div></li><li><div>

anonymous &ndash; Oct 16, 2018<div>

How would you edit this to create an event for, say, the day after (US) Thanksgiving, which is the 4th Thursday of November, but where the next day may actually be the 5th Friday?

</div></div></li><li><div>

anonymous &ndash; Jun 17, 2020<div>

I just put a monthly recurring event starting on the 1st of the month but make the notification 1 day before event, so in effect, it does what you without having to import the ICS file. Only downside is that day of the event is wrong so it is a tradeoff.

</div></div></li></ol>