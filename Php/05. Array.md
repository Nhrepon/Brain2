
module 8.16
## Array count
```php
$numbers = array(1,2,3,4,5,6,7,8,9);
echo count($numbers);
```
## Array walk
```php
$numbers = array(1,2,3,4,5,6,7,8,9);
function square($n){
printf("Square of %d is %d \n", $n , $n*$n);
}
array_walk($numbers, 'square');
```

## Array map
```php
$numbers = array(1,2,3,4,5,6,7,8,9);
function cube($n){
return $n * $n * $n;
}
$cubeArray = array_map('cube', $numbers);
print_r($cubeArray)
```

## Array filter
```php
$numbers = array(1,2,3,4,5,6,7,8,9);
function even($n){
	return $n%2==1;
}
function odd($n){
	return $n%2==1;
}
$oddNumber=array_filter($numbers, 'odd');
$evenNumber=array_filter($numbers, 'even');
print_r(oddNumber);
print_r(evenNumber);


$persons = array ('sujon', 'kabir', 'sabab', 'selim', 'roni', 'jamal', 'kamal', ' sayma'); 

function filterByS ($name){
return $name [0]=='s'; 
}

$newPersons = array_filter($persons, 'filterByS'); 
print_r ($newPersons);
```

## Array reduce
```php
$numbers = array(1,2,3,4,5,6,7,8,9);
function sum($oldValue , $newValue){
	return $oldValue + $newValue
}
$sum=array_reduce($numbers, 'sum');
echo $sum;
```

## Array list
```php
list($red, $green, $blue )=array(122, 233, 65, 34);
echo $red;
```

## Range
```php
$numbers = array();
for($i=12; $i <21 ; $i++){
array_push($numbers, $i);
}
print_r ($numbers); 


foreach(range(11, 20, 2 as $numbers)){
	echo $numbers."\n";
}
```

## Generate random numbers
```php
$numbers = range(40, 72);
echo mt_rand(0, 32);

echo $numbers[$random].""\n';

shuffle($numbers); // shuffle also converts associative array into index array.
print_r ($numbers);


```

## Random in associative array
```php
$fruits = array('a'=>'array', 'b'=>'banana', 'c'=>'apple', 'd'=>'jackfruits', 'e'=>'orange', );
//echo array_rand($fruits);
$key =  array_rand($fruits);
echo $fruits[$key];
```

## A
```php
$n
```

## A
```php
$n
```
## A
```php
$n
```
## A
```php
$n
```
## A
```php
$n
```

## A
```php
$n
```
## A
```php
$n
```
## A
```php
$n
```

## A
```php
$n
```

## A
```php
$n
```
## A
```php
$n
```

## A
```php
$n
```

## A
```php
$n
```
## A
```php
$n
```
## A
```php
$n
```

