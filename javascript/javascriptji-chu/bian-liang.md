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