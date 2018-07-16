# 记录一些基本的知识点备查

## PHP 变量作用域
> 很多语言都以花括号作为作用域界限，PHP中只有函数的花括号才构成新的作用域。

```php
<?php
if (True) {
    $a = 'var a';
}
var_dump($a);
for ($i = 0; $i < 1; $i++) {
    $b = 'var b';
    for ($i = 0; $i < 1; $i++) {
        $c = 'var c';
    }
    var_dump($c);
}
var_dump($b);
var_dump($c);
?>

```
> 可见if和for的花括号并无构成新的作用域。

>闭包作用域跟函数类似，内层不能访问外层变量，外层也不能访问内层变量。
```php
<?php
function a() {
    $test = 'test in a()';
    function b() {
        var_dump($test); // $test不能被访问
        $varb = 'varb in b()';

    }
    b();
    var_dump($varb); // $varb也不能被访问
}
a();

// 输出NULL NULL
?>

```
