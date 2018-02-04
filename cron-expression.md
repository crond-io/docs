# Cron Expression

Schedules are expressed as [cron expressions](https://en.wikipedia.org/wiki/Cron#CRON_expression). The cron expression supported by [crond.io](https://www.crond.io) is the popular _**space-separated five field**_ syntax that represents a set of times as follows:

```
*      *      *      *      *
┬      ┬      ┬      ┬      ┬
│      │      │      │      │
│      │      │      │      └─ Day of week
│      │      │      │  
│      │      │      └──────── Month
│      │      │
│      │      └─────────────── Day of month
│      │
│      └────────────────────── Hour
│
└───────────────────────────── Minute
```

| Field Name | Allowed Values | Allowed Special Characters |
| :--- | :--- | :--- |
| **Day of week** | 0 - 6 or SUN - SAT | **\* / , - L** |
| **Month** | 1 - 12 or JAN - DEC | **\* / , -** |
| **Day of month** | 1 - 31 | **\* / , - L** |
| **Hour** | 0 - 23 | **\* / , -** |
| **Minute** | 0 - 59 | **\* / , -** |

> The month and weekday abbreviations are not case-sensitive.
>
> At most one of 'day of week' or 'day of month' can be a value other than '\*'.

### Slash \(`/`\)

Slashes can be combined with ranges to specify step values.For example, `*/5` in the minutes field indicates every 5 minutes.

> Note that frequencies in general cannot be expressed; only step values which evenly divide their range express accurate frequencies \(for minutes and seconds, that's /2, /3, /4, /5, /6, /10, /12, /15, /20 and /30 because 60 is evenly divisible by those numbers; for hours, that's /2, /3, /4, /6, /8 and /12\); all other possible "steps" and all other fields yield inconsistent "short" periods at the end of the time-unit before it "resets" to the next minute, second, or day; for example, entering \*/5 for the day field sometimes executes after 1, 2, or 3 days, depending on the month and leap year; this is because cron is stateless \(it does not remember the time of the last execution nor count the difference between it and now, required for accurate frequency counting—instead, cron is a mere pattern-matcher\).

### Comma \(`,`\)

Commas are used to separate items of a list. For example, using "MON,WED,FRI" in the 5th field \(day of week\) means Mondays, Wednesdays and Fridays.

### Hyphen \(`-`\)

Hyphens define ranges. For example, 2000-2010 indicates every year between 2000 and 2010, inclusive.

### L

'L' stands for "last". When used in the day-of-week field, it allows you to specify constructs such as "the last Friday" \("5L"\) of a given month. In the day-of-month field, it specifies the last day of the month.

## Examples

| Cron | Meaning |
| :--- | :--- |
| 30 \*/2 \* \* \* | 30 minutes past the hour every 2 hours. |
| 15,45 23 \* \* \* | 11:15 PM and 11:45 PM everyday. |
| 0 1 \* \* SUN | 1 AM every Sunday. |
| 20 16 L \* \* | 4:20 PM on the last day of every month. |
| 20 16 \* \* L5 | 4:20 PM on the last Friday of every month. |
| 20 16 \* \* Lwed-fri | 4:20 PM on the last Wednesay, Thursday and Friday of every month. |



