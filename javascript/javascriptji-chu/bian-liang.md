### 定义变量
`var 变量名 = 值;`  

```js
var a = 100;
```

### 变量的命名规范
1. 只能由英语字母、数字、下划线、美元符号$构成
2. 不能以数字开头
3. 不能是JavaScript保留字
4. js大小写敏感

#### 保留字
```js
abstract、boolean、byte、char、class、const、debugger、double、enum、export、extends、final、float、gotoimplements、import、int、interface、long、native、package、private、protected、public、short、static、super、synchronized、throws、transient、volatile
```

### 变量类型
通过`typeof 变量`，可以检测变量的类型。
#### 数值类型
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

##### 不同进制表示数值
###### 十进制
```js
var a = 10;
```

###### 八进制
```js
//以0开头
var a = 04752;
```

###### 十六进制
```js
//以0x开头
var a = 0x123;
```
 
#### 字符串型
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

##### 连字符和加号
"+" 在js中有两层含义  

1. 连字符
2. 加号

###### 加法
如果加号两边都是数值类型数据，那么就是加法

```js
var a = 100;
var b = 1000;
console.log(a + b);
console.log(10 + 20);
console.log(3.5 + 10);
```

###### 连字符
```js
var a = 100;
var b = 1000;
console.log(a + b);
console.log("a + b");
console.log("a" + "b");
```

#### 布尔型
