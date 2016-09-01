---
title: Using @unless instead of @if statement in Laravel
tip-number: 1
tip-username: Vijayanand
tip-username-profile: https://github.com/vijayanandp
tip-description: Using @unless instead of @if statement in Laravel.

---

Using @unless instead of @if statement in Laravel

We all come across a this situation in which we use 

```php
@if(!Auth::check())
Please Sign in.
@endif
```

In Laravel we have a better solution for this we use

```php
@unless(Auth::check())
Please Sign in.
@endunless
```

We can have another example like this

```php
@unless(count($posts)==0)
<h1>{{$post->title}}</h1>
@endunless
```

the expression checks if it returns FALSE and then shows the data. If the expression returns True it just ignores the inner part.
