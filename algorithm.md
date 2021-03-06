# algorithm

## 排序

### 冒泡排序

**原理：**

* 比较相邻的元素。如果第一个比第二个大，就交换他们两个。
* 对每一对相邻元素做同样的工作，从开始第一对到结尾的最后一对。在这一点，最后的元素应该会是最大的数。
* 针对所有的元素重复以上的步骤，除了最后一个。
* 持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。

```php
function bubbleSort(array $array)
{
    $len = count($array);
    if ($len <= 1) {
        return $array;
    }
    for ($i = 0; $i < $len - 1; $i++) {
        for ($j = 0; $j < $len - $i - 1; $j++) {
            if ($array[$j] > $array[$j + 1]) {
                $temp = $array[$j];
                $array[$j] = $array[$j + 1];
                $array[$j + 1] = $temp;
            }
        }
    }
    return $array;
}
```

## 选择排序

**原理：**

* 每一趟从待排序的元素中选出最小的元素。
* 将选出的元素放在已排好序列的末尾。
* 持续重复上面的步骤，直到全部元素排序完毕。

```php
function selectionSort(array $array)
{
    $len = count($array);
    if ($len <= 1) {
        return $array;
    }
    for ($i = 0; $i < $len -1; $i ++) {
        $min = $i;
        for ($j = $i +1 ; $j < $len; $j ++) {
            if ($array[$min] > $array[$j]) {
                $min = $j;
            }
        }
        if ($min != $i) {
            $temp = $array[$min];
            $array[$min] = $array[$i];
            $array[$i] = $temp;
        }
    }
    return $array;
}
```

