
## String

1. '' quote not parse variable.
3. "" quote parse variable.


```php
$name = "Repon";
$string = "my name is $name \n \t ... "; // my name is repon... next line tab
$string = 'my name is $name \n \t ... '; // my name is $name \n \t ...


// work in multiple line
$heredoc=<<<EOD
ablc
caklhfd {$name} \n
afsldf 
EOD;
echo $heredoc;



// null doc
$heredoc=<<<'EOD'
ablc
caklhfd {$name} \n
afsldf 
EOD;
echo $heredoc;
```