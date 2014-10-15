rps
===

Rsp (Remote Script Protocol) is a PHP extension written in C ++ that allows you to move and perform functions in external scripts without necessarily use the web browser's methods GET, POST or PUT. The send_rsp function allows you to choose the name of the script, the function to be executed, the variable name and the array with the data associated. The call is asynchronous and carried out internally by the Zend Engine. Through the function get_rsp the script to run will receive the data and run. The whole procedure is internal to PHP,  excluding the web server and the user.
Please note that is an unstable version.

API:

SEND_RSP

$var = send_rsp($script_path, $func_name, $var_name, $array);

$script path = location of script (example: script.php or /var/www/script.php)
$func_name = function to be executed (ex: 'myFunc')
$var_name = name of the var(like get or post)
$array = array with data(ex: array('param1' =>'value1', 'param2' => 'value2');

Returns:
TRUE -> all fine!

FALSE -> there was an error with the procedure. The extension will output on the screen the error(or warning) that cause the problem


GET_RSP

$array = get_rsp($var_name);

$var_name = name of var declared in send_rsp function

Returns:
Array() with the data

NULL if something goes wrong

TODO:

-Extend support to PHP classes

-Write an algorithm for avoid internal collision when the different scripts use the same var_name

-Rewrite var shared queue 

-Sanity checks

