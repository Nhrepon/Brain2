### Initial query
```php
$books = DB::table('books')->get();
$authors = DB::table('authors')->limit(3)->offset(2)->get();
$books = DB::table('books')->where('id', 5)->get();

$books = DB::table('books')->where('price', 12)->get();
$books = DB::table('books')->wherePrice(12)->get();
```

### add multiple condition
```php
//where id < 5 and price <=14
$books = DB::table('books')->where([
    ['id', "<=", 5],
    ['price', "<=", 14]
 ])->get();


$books = DB::table('books')
    ->where('id', '<=', 5)
    ->where('price', '<=', 14)
    ->get();
 
```

### Between
```php
$books = DB::table('books')->whereBetween('id', [3, 7])->get();
```

### Where In
```php
$books = DB::table('books')->whereIn('id', [3, 7])->get();
```

### where or where
```php
$books = DB::table('books')->where('id', 3)->orWhere('id', 7)->get();

```


### created at = null
```php
$books = DB::table('books')->whereNull('created_at')->get();

```


### Max
```php
$max = DB::table('books')->max('price');
$maxPricedBook = DB::table('books')->wherePrice($max)->get();

```


### Order by
```php
$books = DB::table('books')->orderBy('title')->get();
$books = DB::table('books')->orderBy('price','desc')->get();

$books = DB::table('books')->orderBy('price','desc')->limit(1)->get();
$books = DB::table('books')->orderBy('price','desc')->first();
```


### Join with authors and display author name
```php
$books = DB::table('books')
    ->join('authors', 'books.author_id', '=', 'authors.id')
    ->select('books.title', 'authors.name as author_name','books.author_id','books.id as book_id')
    ->get();
```


### Find all books from author id 1
```php
$books = DB::table('books')
    ->join('authors', 'books.author_id', '=', 'authors.id')
    ->select('books.title', 'authors.name as author_name','books.author_id','books.id as book_id')
    ->where('author_id',1)
    ->get();
```


### Display SQL
```php
$books = DB::table('books')
    ->join('authors', 'books.author_id', '=', 'authors.id')
    ->select('books.title', 'authors.name as author_name','books.author_id','books.id as book_id')
    ->where('author_id',1)
    ->toSql();
```

### Find books of all authors but author id 2
```php

$books = DB::table('books')
    ->join('authors', 'books.author_id', '=', 'authors.id')
    ->select('books.title', 'authors.name as author_name', 'books.author_id', 'books.id as book_id')
    ->whereNotIn('author_id', [2])
    ->get();

```

### Find max priced book and books where price between 12 to 14
```php

$max = DB::table('books')->max('price');
$books = DB::table('books')
    ->join('authors', 'books.author_id', '=', 'authors.id')
    ->select('books.title', 'authors.name as author_name', 'books.author_id', 'books.id as book_id', 'price')
    ->wherePrice($max)
    ->orWhereBetween('price', [12, 14])
    ->get();
```

### Left join and right join
```php
$books = DB::table('books')
    ->rightJoin('authors', 'books.author_id', '=', 'authors.id')
    ->select('books.title', 'authors.name as author_name', 'books.author_id', 'books.id as book_id')
    ->orderBy('books.title', 'desc')
    ->get();
```

### Count
```php
$count = DB::table('books')->count();

if(count($books)==0){
    $books =
    }
```

### Insert
```php
DB::table('authors')->insert([
    'name' => 'Jack London',
    'bio' => 'American author and short story writer.'
    ]);
```

### Insert and get id
```php
$newAuthorId = DB::table('authors')->insertGetId([
    'name' => 'Henry Rider Haggard',
    'bio' => 'American author and short story writer.'
    ]);
```

### Insert author and book at once
```php
DB::table('books')->insert([
    'title' => 'Alan Quantermain',
    'author_id' => $newAuthorId,
    'price' => 12
    ]);
```

### Update
```php
DB::table('books')->whereId(10)->update([
    'price'=>20
    ]);
```

### Delete
```php
DB::table('books')->where('price', '>', 14)->delete();
```

### 
```php


```

### 
```php


```
### 
```php


```

### 
```php


```

