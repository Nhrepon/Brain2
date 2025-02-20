```php
$html = file_get_contents("www.google.com");

libxml_use_internal_errors(true);
$dom = new DOMDocument;
$dom -> loadHTML($html);
libxml_clear_errors();

$xPatch = new DOMXPath($dom);
$values = $xPath->query('//h1[contains(@class, "juba")]');

foreach($values as $item){
	echo $dom->saveHTML($item); // for html
	echo $item->textContent; // for value as text
	echo '<br/>';
}





```


