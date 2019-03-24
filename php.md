# PHP

# 基础部分

**基础知识必须掌握，尤其需要注意细节**

* 用 PHP 获取当前时间并打印,打印格式:2019-3-23 22:21:21

```php
date_default_timezone_set('PRC');//设置时区
echo date('Y-n-d H:i:s');//这里使用 n，m 和 n 的区别是：n 没有前导零而 m 有前导零
```

* cookie 和 session 的区别和关系

> 1. cookie 存储在客户端，session 存储在服务端
> 2. session 安全性比 cookie 高
> 3. 单个 cookie 保存的数据不能超过 4KB
> 4. 如果客户端（浏览器）禁用了 cookie，session 也会失效。但是可以通过传递 session id 保证 session 依然可用

* echo，print，print_r，var_dump 的区别

> echo、print 是 PHP 的语句（语言结构），var_dump 和 print_r 是函数
>
> echo 输出一个或多个字符串，中间用逗号分隔，没有返回值
>
> print 有返回值，仅支持一个参数
>
> var_dump 和 print_r 都可以输出复杂变量类型的值
>
> var_dump 可以输出变量类型，长度，因此更适合调试

* isset 和 empty 的区别

> empty 如果 `var` 存在，并且是一个非空非零的值时返回 **FALSE** 否则返回 **TRUE**
>
> isset 如果 `var` 存在并且值不是 **NULL** 则返回 **TRUE**，否则返回 **FALSE**。

* 单引号和双引号的区别

> 一般情况下两者通用，但双引号内部变量会被解析，单引号则不解析。

* 传值和传引用的区别

> 变量默认总是传值赋值 。PHP 也提供了另外一种方式给变量赋值:引用赋值。这意味着新的变量简单的引用(换言之，“成为其别名” 或者 “指向”)了原始变量。改动新的变量将影响到原始变量 ，反之亦 然。使用引用赋值，简单地将一个 & 符号加到将要赋值的变量前(源变量)。
>
> 对象默认是传引用。
>
> 对于较大的数据，传引用比较好 ，这样可以节省内存的开销。

* 反转字符串

```php
$str = "abc";
echo strrev($str) . PHP_EOL; //使用php内置函数

//自定义函数实现
function example(string $str)
{
    $len = strlen($str);
    $out = '';
    for ($i = $len - 1; $i >= 0; $i--) {
        $out .= $str[$i];
    }
    return $out;
}

echo example($str) . PHP_EOL;
```

* 写一个函数将字符串 `open_door`  转换成  `OpenDoor`

```php
$str = 'open_door';

function example(string $str)
{
    $arr = explode('_', $str);
    foreach ($arr as $key => $value) {
        $arr[$key] = ucfirst($value);
    }
    return implode('', $arr);
}

echo example($str) . PHP_EOL;
```

* PHP 处理字符串的常用函数
* PHP 处理数组的常用函数
* PHP 处理时间的常用函数