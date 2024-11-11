Table name brands and model name brand
Table product_details and model name ProductDetails

```php

protected $table = 'brands';
protected $primaryKey = 'id';

protected $attributes =[
'brandName'=>'brand'
]
```

## Make Model with migration
```php
php artisan make:task -m 

edit migration

php artisan migrate

php artisan make:controller TaskController

php artisan make:seeder taskSeeder

edit taskSeeder:

class taskSeeder extends Seeder
{
    public function run(): void
    {
		task::truncate(); // to empty table
		
        for ($i = 0; $i < 10; $i++) {

            task::create([

                'title' => fake()->sentence(10),

                'description' => fake()->sentence(20),

                'due_date' => now()->addDays(rand( 1, 10 ))

            ]);

        }

    }

}

add taskSeeder to Database seeder:
class DatabaseSeeder extends Seeder

{

    public function run(): void

    {

        // User::factory(10)->create();

  

        /* User::factory()->create([

            'name' => 'Test User',

            'email' => 'test@example.com',

        ]); */

        $this->call(taskSeeder::class);

    }

}

php artisan db:seed



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
```