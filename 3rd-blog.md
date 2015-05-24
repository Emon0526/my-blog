本文主要记录lodash中关于 Array 部分的一些方法的使用。

首先，什么是lodash呢？

lodash，是一个 JavaScript 实用工具库，提供一致性，模块化，性能和配件等功能。

1、_.chunk(array,[size=1]) 按指定长度合并数组中的元素。

有两个参数：

array (Array): 数组

[size=1](number): 每个块的长度

例如：

```
_.chunk(['a', 'b', 'c', 'd'], 2); // → \[['a', 'b'], ['c', 'd']]

_.chunk(['a', 'b', 'c', 'd'], 3); // → \[['a', 'b', 'c'],
```

2、_.compact(array) 删除数组中的虚假值。如null,false,0,undefined,NaN

有一个参数：

array(Array)：数组

例如：

```
_.compact([0, 1, false, 2, '', 3]);  

// → [1, 2, 3]
```

3、_.difference(array,[values]) 排除第一个数组中与第二个数组元素中相同的元素

有两个参数：

array(Array)：要执行检查的数组

[values](Array)：用来排除的值

例如：

```
_.difference([1, 2, 3], [4, 2]); // → [1, 3]
```

4、_.intersection([arrays]) 找到几个数组中共有的元素并输出

有一个参数：

array(Array)：要执行检查的元素

例如：

```
_.intersection([1, 2], [4, 2], [2, 1]); // → [2]
```

5、_.first(array) 输出数组的第一个元素

_.rest(array)输出数组除第一个元素剩下的元素

_.last(array)输出数组的最后一个元素

_.initial(array)输出数组除最后一个元素剩下的元素

例如：

```
_.first([1, 2, 3]);  
// → 1  
_.first([]);  
// → undefined  
输出第一个元素  
_.rest([1, 2, 3]);  
// → [2, 3]  
输出除第一个元素的剩下元素。  
_.last([1, 2, 3]);  
// → 3  
输出最后一个元素。  
_.initial([1, 2, 3]);  
// → [1, 2]  
输出除最后一个元素的剩下元素。
```

6、_.without(array,[values]) 过滤掉values 后输出新的数组

有两个参数：

array(Array)：要执行检查的数组

[values](...)：用来排除的值

例如：

```
_.without([1, 2, 1, 3], 1, 2); // → [3]
```

7、_.xor([arrays])都有的留下，只有一个的留下，其余的删掉，并合并为新数组。

有一个参数：

array(Array)：要执行检查的数组

例如：

```
_.xor([1, 2], [4, 2]); // → [1, 4]

_.xor([1, 2, 3], [5, 2, 1, 4]);  
// → [3, 5, 4]

_.xor([1, 2, 5], [2, 3, 5], [3, 4, 5]);  
// → [1, 4, 5]
```

8、_.zip([arrays])从两个数组的对应位置取出数据并合并为新数组。

有一个参数：

array(Array)：要执行检查的数组

例如：

```
_.zip(['fred', 'barney'], [30, 40], [true, false]);

// → \[['fred', 30, true], ['barney', 40, false]]
```

9、_.unzip([arrays])从两个数组的对应位置取出数据并合并为新数组。

有一个参数：

array(Array)：要执行检查的数组

例如：

```
var zipped = _.zip(['fred', 'barney'], [30, 40], [true, false]);

// → \[['fred', 30, true], ['barney', 40, false]]

_.unzip(zipped); // → \[['fred', 'barney'], [30, 40], [true, false]]
```

10、_.indexOf(array,value,[formIndex=0])返回，之后数据出现的首次位置，计数从0开始。

有三个参数：

array(Array)：要搜索的数组

value(_)：搜索的值

[formIndex=0](boolean|number)：搜索的索引

返回值：

(number)：返回匹配的索引值，未找到则返回-1.

例如：

```
_.indexOf([1, 2, 1, 2], 2); // → 1

// using `fromIndex`_.indexOf([1, 2, 1, 2], 2, 2); // → 3

// performing a binary search_.indexOf([1, 1, 2, 2], 2, true); // → 2
```

11、*.remove(array,[predicate=*.identity],[thisArg])

有三个参数：

array(Array)：要修改的数组

[predicate=_.identity](function/object/string)调用每个迭代函数

[tihsArg](*)：这个绑定的谓词。

例如：

```
var array = [1, 2, 3, 4];  
var evens = _.remove(array, function(n) { return n % 2 == 0; });

console.log(array);  
// → [1, 3]

console.log(evens);  
// → [2, 4]
```

---

原文链接：http://my.oschina.net/u/2362030/blog/418920
