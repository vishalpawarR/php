# php
 php notes

## Hello World :
```php
<!DOCTYPE html>
<html>
<body>

<?php
echo "Hello World!";
?>

</body>
</html>
```

## Variables :
we can declare a variable in php. the variable name should start with `$`
```php
<!DOCTYPE html>
<html>
<body>

<?php
$txt = "PHP";
echo "I love $txt!";
?>

</body>
</html>
```
> Note: To print the variable value we need to use the `$` sign before variable name.
> Note: The variable declare out side function called as global variable.

## `global` keyword :
this keyword is used to access the global variable of the php.
```php
<!DOCTYPE html>
<html>
<body>

<?php

$y = 1;
$x = 2;

function sum() {
	global $x, $y;
    $x = $x + $y;
}
sum();
echo $x;
?>

</body>
</html>
```
> Note: php stores the global variable in the array named $GLOBALs[index]. We can use this array to access all the global variables. in place of index pass the variable name in string format to access the elements.
```php
<!DOCTYPE html>
<html>
<body>

<?php

$y = 1;
$x = 2;

function sum() {
	$GLOBALS['x'] = $GLOBALS['x'] + $GLOBALS['y'];
}
sum();
echo $x;
?>

</body>
</html>
```

## `static` keyword :
* Whenever we call method the values of that variable is lost. we can change this using static keyword.
```php
<!DOCTYPE html>
<html>
<body>

<?php
function sum() {
	static $x = 10;
    $x++;
    return $x;
}
echo sum();
echo "<hr>";
echo sum();
echo "<hr>";
echo sum();
echo "<hr>";
echo sum();
echo "<hr>";
echo sum();
echo "<hr>";
?>

</body>
</html>
/*
output :
11
12
13
14
15
*/
```

## print and echo in php:
Both of them can be used to output the value on screen but the echo is faster than print.

[About `echo` and `print`](https://www.w3schools.com/php/php_echo_print.asp#:~:text=echo%20and%20print%20are%20more,print%20can%20take%20one%20argument.)

## datatypes :
1. String : can be enclosed between single or double statement.
1. Integer
1. Float
1. Array
1. Null
1. Boolean
1. Object

## Array :
* Are can be used to store multiple values in the one place.
* we can create an array using `array()`.
```php
<!DOCTYPE html>
<html>
<body>

<?php  
$cars = array("Volvo","BMW","Toyota");
var_dump($cars);
?>  

</body>
</html>
/*
output :
array(3) {
  [0]=>
  string(5) "Volvo"
  [1]=>
  string(3) "BMW"
  [2]=>
  string(6) "Toyota"
}
*/
```
## Object and class :
* We can declare a class like this below
```php
<!DOCTYPE html>
<html>
<body>

<?php
class Car {
  public $color;
  public $model;
  public function __construct($color, $model) {
    $this->color = $color;
    $this->model = $model;
  }
  public function message() {
    return "My car is a " . $this->color . " " . $this->model . "!";
  }
}

$myCar = new Car("black", "Volvo");
echo $myCar -> message();
echo "<br>";
$myCar = new Car("red", "Toyota");
echo $myCar -> message();
?>

</body>
</html>

/*
output :
My car is a black Volvo!
My car is a red Toyota!
*/
```

## String :
* To find the length of string `strlen()`.
```php
<!DOCTYPE html>
<html>
<body>

<?php
$name = "Vishal";
echo(strlen($name)); //6
?>

</body>
</html>
```
* `str_word_count()` - Count Words in a String.
```php
<!DOCTYPE html>
<html>
<body>

<?php
$name = "Vishal pawar developer";
echo(str_word_count($name));//3

?>

</body>
</html>
```
* `strrev()` - Reverse a String.
```php
<!DOCTYPE html>
<html>
<body>

<?php
echo strrev("Hello world!"); // outputs !dlrow olleH
?>

</body>
</html>
```
* `strpos()` - Search For a Text Within a String
returns index if found or else it will return false.
```php
<!DOCTYPE html>
<html>
<body>

<?php
echo strpos("Hello world!", "world"); // outputs 6
?>

</body>
</html>
```
* `str_replace()` - Replace Text Within a String.
```php
<!DOCTYPE html>
<html>
<body>

<?php
echo str_replace("world", "Dolly", "Hello world!"); // Hello Dolly
?> 
 
</body>
</html>
```
## constant variable :
* The constant variable can be declared like as shown below.
```php
define(name, value, case-insensitive)

Parameters:

name: Specifies the name of the constant
value: Specifies the value of the constant
case-insensitive: Specifies whether the constant name should be case-insensitive. Default is false
```
example :
```php
<!DOCTYPE html>
<html>
<body>

<?php
// case-insensitive constant name
define("GREETING", "Welcome to W3Schools.com!", true);
echo greeting;
?> 

</body>
</html>
```
## Operators : 
* The operators are like the javascript.
[Operator notes](https://www.w3schools.com/php/php_operators.asp)
## Condition statement :
```php
<!DOCTYPE html>
<html>
<body>

<?php
$t = date("H");
echo "<p>The hour (of the server) is " . $t; 
echo ", and will give the following message:</p>";

if ($t < "10") {
  echo "Have a good morning!";
} elseif ($t < "20") {
  echo "Have a good day!";
} else {
  echo "Have a good night!";
}
?>
 
</body>
</html>
```

## Loops :
Loop syntax is same as javascipt [Notes](https://www.w3schools.com/php/php_looping.asp)
