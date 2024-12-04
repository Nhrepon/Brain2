```php
php artisan make:middleware Auth

//to implement middleware in multiple route, add middleware into karnel.php middleware aliases.

Route::middleware([auth])->group(function(){all route goes here} );

// to implement middleware in full route file, add middleware into karnel.php middleware groups.


```

## Rate limiting
```php
middleware('throttle:50, 1');

// use it into karnel.php for implement in route group
'throttle:50, 1' // count, minutes

```

