---
title: Cache Database Queries
tip-number: 3
tip-username: Vijayanand
tip-username-profile: https://github.com/vpvijayanand
tip-description: Cache Database Queries.

---

Lets take an example of product billing in which the price of the product remains almost the same through out the day. The changes that takes place in the table is very low but it is very fequently used in billing.
In this situation we may have to freqently get the price from the table which will lead too many database queries. Laravel offers a simple way for caching these queries. Which can be done as a single method call.

We will grab all the price of the products from the database, but cache the query.
```php
$price = Price::remember(60)->get();
```
Now for the next one hour of page requests, that query will remain in cache and the database will not be touched.
