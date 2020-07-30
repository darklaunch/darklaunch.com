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
https://www.darklaunch.com/2016/06/13/google-calendar-last-day-of-month-repeat