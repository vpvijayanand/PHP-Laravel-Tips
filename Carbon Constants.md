---
title: Using Carbon Constants
tip-number: 2
tip-username: Vijayanand
tip-username-profile: https://github.com/vpvijayanand
tip-description: Using Carbon Constants.

---

We use awesome Carbon Class when we work with dates and times. Many of us don't go deep into it and see there are many constants that can help us a lot while programming. 

Say If I want to send a remainder mail for a blog update on every Thursday then

```php
if ($dt->dayOfWeek == Carbon::THURSDAY) // ... do some Task

if ($dt->dayOfWeek == Carbon::THURSDAY) // ... do some Task
```

There are constants for all days of week:

```php
var_dump(Carbon::SUNDAY);                          // int(0)
var_dump(Carbon::MONDAY);                          // int(1)
var_dump(Carbon::TUESDAY);                         // int(2)
var_dump(Carbon::WEDNESDAY);                       // int(3)
var_dump(Carbon::THURSDAY);                        // int(4)
var_dump(Carbon::FRIDAY);                          // int(5)
var_dump(Carbon::SATURDAY);                        // int(6)
```

There are also constants for how much years in a century or hours in a day.

```php
var_dump(Carbon::YEARS_PER_CENTURY);               // int(100)
var_dump(Carbon::YEARS_PER_DECADE);                // int(10)
var_dump(Carbon::MONTHS_PER_YEAR);                 // int(12)
var_dump(Carbon::WEEKS_PER_YEAR);                  // int(52)
var_dump(Carbon::DAYS_PER_WEEK);                   // int(7)
var_dump(Carbon::HOURS_PER_DAY);                   // int(24)
var_dump(Carbon::MINUTES_PER_HOUR);                // int(60)
var_dump(Carbon::SECONDS_PER_MINUTE);              // int(60)
```

Hope this tip will make you learn more on the Carbon constants
