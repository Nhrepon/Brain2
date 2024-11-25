
```php

Route::get("/user-registration", [controller::class, 'userRegistration'])->middleware([]);


Route::get("/user-registration/{id}", [controller::class, 'userRegistration']);


```