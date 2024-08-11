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

## Create controller with resource
```php
php artisan make:controller TaskController1 -r

```

## Show route list
```php
php artisan route:list
```


## Make component with layout
```php
php artisan make:component layout --view

php artisan make:component tasks.index

php artisan make:component tasks.index --view
```

## Migration
```php

php artisan migrate

//create table
php artisan make:migration create_contacts_table

// Undo migration
php artisan migrate:rollback

// add section to existing table
php artisan make:migration add_section_to_contacts_table

// Reset all migration
php artisan migrate:reset

// Rename table column
php artisan make:migration rename_column_to_contacts_table
$table->renameColumn('name', 'contacts_name');

// Enable index
php artisan make:migration add_index_to_contacts_table
$table->index('name');

$table->string('email')->index();
$table->text('description')->fullText();

rollback: $table->dropIndex('name');



```

## Make model
```php
php artisan make:model task

// with migration
php artisan make:task -m 
```

## a
```php

```

## a
```php

```

## a
```php

```

## a
```php

```

## a
```php

```
## a
```php

```

## a
```php

```
## a
```php

```
## a
```php

```
## a
```php

```

