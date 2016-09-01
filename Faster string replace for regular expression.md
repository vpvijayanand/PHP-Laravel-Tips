---
title: Faster string replace for regular expression.
tip-number: 5
tip-username: Vijayanand
tip-username-profile: https://github.com/vpvijayanand
tip-description: Faster string replace for regular expression.

---

If we compare the execution time for **str_replace()** with that of **ereg_replace()** and **preg_replace()** when we do for a regular expression. We can see that **ereg_replace()** and **preg_replace()** are much faster then **str_replace()**. Because **str_replace()** does not support pattern matching. 

So always see that if you need to match a pattern, use a regular expression function. If you need to match a string, use a string function.
