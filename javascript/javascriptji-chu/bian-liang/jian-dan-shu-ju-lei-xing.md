### 种类
1. Number
2. String
3. Boolean
4. undefined

特殊值： null

### 数值类型
JavaScript中，只要是个数，那么就是数值型的，无论整浮、无论大小、无论正负，都是number类型的。  

```js
var a = 100;
var b = 232323232323232323;
var c = 1.030300303;
var d = -123123;
var f = 0.324;

console.log(typeof a);
console.log(typeof b);
console.log(typeof c);
console.log(typeof d);
console.log(typeof f);
```

#### 数值范围
由于内存的限制，ECMAScript 并不能保存世界上所有的数值：  

1. 最小值：Number.MIN_VALUE，这个值为： 5e-324
2. 最大值：Number.MAX_VALUE，这个值为： 1.7976931348623157e+308
3. 无穷大：Infinity
4. 无穷小：-Infinity

#### NaN

1. NaN 非数值（Not a Number的简写）  
  console.log(“abc”/18);  //结果是NaNUndefined和任何数值计算为NaN;NaN 与任何值都不相等，包括 NaN 本身
2. isNaN() :任何不能被转换为数值的值都会导致这个函数返回 true   
  （isNaN译为是否符合一个标准，什么标准呢？不是一个数字的标准，如果符合了那么就不是一个数字，不符合就是一个数字）  
    ```js
    isNaN(NaN);// true  
    isNaN(“blue”); // true  
    isNaN(123); // false
    ```
    
#### 不同进制表示数值
##### 十进制
```js
var a = 10;
```

##### 八进制
```js
//以0开头
var a = 04752;
```

##### 十六进制
```js
//以0x开头
var a = 0x123;
```
 
### 字符串型
```js
var a = "a";
var b = "中文字符串";
var c = "123123";
var d = "啊哈哈哈";
var f = "";

console.log(typeof a);
console.log(typeof b);
console.log(typeof c);
console.log(typeof d);
console.log(typeof f);
```

#### 连字符和加号
"+" 在js中有两层含义  

1. 连字符
2. 加号

##### 加法
如果加号两边都是数值类型数据，那么就是加法

```js
var a = 100;
var b = 1000;
console.log(a + b);
console.log(10 + 20);
console.log(3.5 + 10);
```

##### 连字符
```js
var a = 100;
var b = 1000;
console.log(a + b);
console.log("a + b");
console.log("a" + "b");
```

### 布尔型
只有两种`true false`  

```js
var a = true;
var b = false;
console.log(a);
console.log(b);
console.log(typeof a);
console.log(typeof b)
```

