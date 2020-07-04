Create calendar event for Thanksgiving celebrated on the fourth Thursday of November.

Create a new ics (iCalendar) file like "thanksgiving.ics".

```
BEGIN:VCALENDAR
BEGIN:VEVENT
RRULE:FREQ=YEARLY;INTERVAL=1;BYMONTH=11;BYDAY=4TH
DTSTART;VALUE=DATE:20161124
DTEND;VALUE=DATE:20161125
SUMMARY:Thanksgiving title here.
DESCRIPTION:Thanksgiving description here.
END:VEVENT
END:VCALENDAR
```