### 什么是高阶函数
JavaScript的函数其实都指向某个变量。既然变量可以指向函数，函数的参数能接收变量，那么一个函数就可以接收另一个函数作为参数，这种函数就称之为高阶函数。

#### 高阶函数案例
编写高阶函数，就是让函数的参数能够接收别的函数。

```js
function toInt(x) {
    if(x < 0) {
        return -x;
    }else {
        return x;
    }
}

function add(x, y, f) {
    return f(x) + f(y);
}

add(-2, 5, toInt); // 7
```

### map
map方法定义在Array中，可以接受函数作为参数,返回一个新数组，原数组不变。

```js
如果想把数组里面所有的数加1

var arr = [1, 2, 3, 4, 5, 6, 7];

function addOne(x) {
    return x + 1;
}

var anies = arr.map(addOne);
console.log(anies);
```

### reduce
Array的`reduce()`把一个函数作用在这个Array的`[x1, x2, x3...]`上，这个函数必须接收两个参数，`reduce()`把结果继续和序列的下一个元素做累积计算

```js
[x1, x2, x3, x4].reduce(f);
等价于：
f(f(f(x1, x3), x3), x4);
```

#### 对数组中的数据求和
```js
var arr = [1, 2, 3, 4, 5]
var sum = arr.reduce((x1, x2) => x1 + x2);
console.log(sum);
```

### filter
filter也是一个常用的操作，它用于把Array的某些元素过滤掉，然后返回剩下的符合条件的元素。

filter()把传入的函数依次作用于每个元素，然后根据返回值是true还是false决定保留还是丢弃该元素。

```js
将数组中的偶数筛选出来

var arr = [1, 2, 3, 4, 5, 6, 7];
var arr2 = arr.filter(x => x % 2 == 0);
//或者
var arr2 = arr.filter(function(x) {
    return x %2 == 0; 
})
console.log(arr2);
```

### sort 
Array默认的sort排序方法有时会不尽人意，

1. 字符串根据ASCII码进行排序
2. sort()方法默认把所有元素先转换为String再排序

```js
// 看上去正常的结果:
['Google', 'Apple', 'Microsoft'].sort(); // ['Apple', 'Google', 'Microsoft'];

// apple排在了最后:
['Google', 'apple', 'Microsoft'].sort(); // ['Google', 'Microsoft", 'apple']

// 无法理解的结果:
[10, 20, 1, 2].sort(); // [1, 10, 2, 20]
```
