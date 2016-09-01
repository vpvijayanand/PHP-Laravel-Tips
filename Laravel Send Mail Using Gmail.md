---
title: Laravel Send Mail Using Gmail
tip-number: 4
tip-username: Vijayanand
tip-username-profile: https://github.com/vpvijayanand
tip-description: Laravel Send Mail Using Gmail.

---
As Mandrill by Mailchimp is going to change as a paid version hope this tip will help you out. 

```php
use \Swift_Mailer;
use \Swift_SmtpTransport as SmtpTransport;

$smtpTransport = SmtpTransport::newInstance('smtp.gmail.com', 587, 'tls');
$smtpTransport->setUsername('yourMailId@gmail.com');
$smtpTransport->setPassword('yourPasswordForGmail');

$gmail = new Swift_Mailer($smtpTransport);

// Assign it to the Laravel Mailer and Send Message
Mail::setSwiftMailer($gmail);

Mail::send();
