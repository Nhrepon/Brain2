```php
date_default_timezone_set("Asia/Dhaka");
date('dS F, Y h:i:s A');

echo date('z');
echo date('t');

echo mktime(0, 0, 0, 12, 12, 1980);
echo strtotime("12 December, 1980");


$d1 = new DateTime('08 June 1993');
$d2 = new DateTime('08 June 2024');
$difference = $d1->diff($d2); // date_diff($d1, $d2);
echo $difference->format("%y years %m months %d days.");






```