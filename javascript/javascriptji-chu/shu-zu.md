### 什么是数组
数组是一种数据类型。（把很多数据装入一个盒子中，用的时候在取出来）

### 为什么使用数组
存储多个值的时候，使用数组，每一个索引对应一个值，用来存储一系列值，方便快捷。

### 定义数组
#### 字面量定义

```js
var arr = [1, 2, 3];
var arr2 = ["1", "2", "3"];
```

#### 对象定义

```js
var  arr  =  new Array(参数);
参数位置一个数值时为数组长度，多个数值时为数组中的元素。
```

### 数组操作
#### length操作
##### 获取长度

```js
数组的长度 = 数组名.length;

var arr = [1, 2, 3,  "5"];
var len = arr.length;
```

##### 修改长度
可以通过修改数组的长度来改变数组中元素的个数，如果改小了，数组从后面删除元素。  
**（伪数组的长度可以修改，但是不能修改里面的元素）**

```js
var arr2 = [1, 2, 3, 4];
arr2.length = 6;
// arr2 变为 [1, 2, 3, 4, undefined, undefined];
arr2.length = 2;
// arr2 变为 [1, 2];
```

##### 获取元素

```js
数组中的指定元素 = 数组名[索引值];
果获取数组中元素是，数组名[索引值]，没有指定索引（元素没那么多），系统不报错，而是给定值为undefined；

var arr = [1, 2, 3,  "5"];
var a = arr[1]; // a = 2;
var b = arr[3]; // b = "5";
var c = arr[6]; // c = undefined;
```

#### 修改元素
将对应位置的值修改
如果通过索引赋值时，索引超过了范围，同样会引起Array大小的变化

```js
数组名[索引值] = 要修改成的值;

var arr = [1, 2, 3,  "5"];
arr[1] = 10; // arr变为 [1, 10, 3, "5"];
arr[6] = 12; // arr变为 [1, 10, 3, "5", undefined, undefined, 12];
```

#### indexOf(查询元素在数组的索引)
语法： `array.indexOf(值);`,找不到返回-1;

```js
var arr = [1, 2, 3, "1", "2"];
arr.indexOf(2); //1
arr.indexOf(1); //0
arr.indexOf("1"); //3
arr.indexOf(1222); //-1
```

#### slice(截取数组)
截取Array的部分元素，然后返回一个新的Array, slice()的起止参数包括开始索引，不包括结束索引  

```js
var arr = [1, 2, 3, 4, 5, 6];
//从0开始截取，到3结束，但是不包括3
var newArr = arr.slice(0, 3); // newArr = [1, 2, 3]
//从3开始截取，一直到结束
var newArr2 = arr.slice(3); // newArr2 = [4, 5, 6];
//不传参数，相当于从头到尾截取，相当于复制一个数组
var newArr3 = arr.slice(); // newArr3 = [1, 2, 3, 4, 5, 6];
```

#### push与pop
`push()`向`Array`的末尾添加若干元素，`pop()`则把`Array`的最后一个元素删除掉,返回数组的新长度.

```js
var arr3 = [1, 2];
arr3.push(5);
arr3.pop();
console.log(arr3.push(2, 3, 4));
console.log(arr3.pop());
```

#### unshift与shift
使用`unshift()`方法往`Array`的头部添加若干元素，`shift()`方法则把`Array`的第一个元素删掉,返回数组的新长度.

```js
var arr3 = [1, 2];
arr3.unshift(5);
arr3.shift();
console.log(arr3.unshift(2, 3, 4));
console.log(arr3.shift());
```

#### sort(排序)
`sort()`可以对当前`Array`进行排序，它会直接修改当前`Array`的元素位置，直接调用时，按照默认顺序排序  

```js
var arr3 = [3, 2, 5];
arr3.sort(); // arr3变为 [2, 3, 5];
```

#### reverse(反转)

```js
var arr3 = [3, 2, 5];
arr3.reverse();
```

#### splice
可以从指定的索引开始删除若干元素，然后再从该位置添加若干元素,返回删除的元素

```js
var arr4 = ['a', 'b', 'c', 'd', 'e'];
console.log(arr4);
//从索引1开始，删除2个元素，然后再添加3个元素
arr4.splice(1, 2, 'f', 'g', 'h');
console.log(arr4); //["a", "f", "g", "h", "d", "e"]

//从索引2开始删除2个元素，不添加元素;
arr4.splice(2, 2);
console.log(arr4); //["a", "f", "d", "e"]

//只添加不删除
arr4.splice(2, 0, 'i', 'j');
console.log(arr4); //["a", "f", "i", "j", "d", "e"]
```

#### contact(连接)
`contact`用于将当前的`array`和另一个`array`连接起来,返回一个新数组。