---
title: Configure Phpmyadmin with AWS RDS
tip-number: 6
tip-username: Vijayanand
tip-username-profile: https://github.com/vijayanandp
tip-description: Configure Phpmyadmin with AWS RDS.

---
```php
Step 1 : sudo apt-get install phpmyadmin
```
```php

Step 2 : vim /etc/apache2/apache2.conf
```
Add the below 2 lines at the end of the file

```php    
# phpMyAdmin Configuration
Include /etc/phpmyadmin/apache.conf
```

```php
Step 3: vi /etc/phpmyadmin/config.inc.php
```
Add the below lines after
$i++;
}

```php
$cfg['Servers'][$i]['auth_type'] = 'HTTP';
$cfg['Servers'][$i]['hide_db'] = '(mysql|information_schema|phpmyadmin)';
/* Server parameters  change the host name as required*/
$cfg['Servers'][$i]['host'] = 'XXXXXXXXXX.cczxwknzymwh.us-west-2.rds.amazonaws.com';
```

```php
Step 4: service apache2 restart
```
