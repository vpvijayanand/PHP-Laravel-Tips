---
title: Laravel - How to get table name from modal
tip-number: 10
tip-username: Vijayanand
tip-username-profile: https://github.com/vpvijayanand
tip-description: Laravel -How to get table name from modal.md

---

We can get table name simply by using a call getTable() of model object.

Example:

```php
$item = new Item;
$table = $item->getTable();
print_r($table);
