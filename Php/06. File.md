
```php
fopen
fclose

$fp = fopen($filename, "r / w / r+ / w+ / a / a+");

array to file:
fputcsv($fp, $student);

fgets($fp);
fgetscsv($fp);

file_put_contents

print_r(file($filename));

$data = serialize($students);
file_put_contents($filename, $data, LOCK_EX); // to write data in serilize way.

$data = json_encode($students);
file_put_contents($filename, $data, LOCK_EX); // to write data in json format.

session_name("mysession");
session_start([
'cookie_lifetime'=>60;
]);
$_SESSION['name']='Repon';
echo $_session("name");


setcookie("name", "value", time()+300 , "path");







```


