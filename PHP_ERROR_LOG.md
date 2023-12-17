## type and value of a variable

```php
$message = "Variable \$value: Type: " . gettype($value) . ", Value: " . var_export($value, true);

error_log($message);


```
