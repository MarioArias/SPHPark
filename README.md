# SPHPark
PHP support for Spark
```php
<?php

$sc = new SPHParkContext();
$text_file = $sc->text_file("hdfs://");
$counts = $text_file->flat_map(function ($line) {
    return $line->split("");
})->map(function ($word){
    return array($word,1);
})->reduced_ByKey(function($a,$b){
    return $a + $b;
});

$counts->saveAs_TextFile("hdfs://");    
```

# Happy April Fools' day
