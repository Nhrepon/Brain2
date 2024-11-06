```php
throw new Exception("", 1001);

try{

}catch(Exception $e){
echo $e->getCode().":".$e->getMessage();
}



```