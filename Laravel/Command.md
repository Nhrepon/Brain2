```php
// create laravel app
composer create-project laravel/laravel:^10.0 Laravel10Demo

// to start app
php artisan serve

// model
php artisan make:task -m 

edit migration

php artisan migrate

php artisan make:controller TaskController

php artisan make:seeder taskSeeder


```

# Create controller with resource
```php
php artisan make:controller TaskController1 -r

```

# Show route list
```php
php artisan route:list
```


# Make component with layout
```php
php artisan make:component layout --view

php artisan make:component tasks.index

php artisan make:component tasks.index --view

