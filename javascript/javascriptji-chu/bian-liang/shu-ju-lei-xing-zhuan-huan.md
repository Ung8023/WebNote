### 几种转换
1. 简单类型转成字符串
2. 简单类型转成数值
3. 简单类型转成布尔

### 简单类型转字符串
#### 通过连字符
变量 + 字符串(可以为任意字符串，空串也可以); 

```js
var a = 10;
var b = 12.30;
var c = true;

console.log(typeof (a + ""));
console.log(typeof (b + ""));
console.log(typeof (c + ""));
```

#### 通过String(变量)

```js
console.log(typeof (String(a)));
console.log(typeof (String(b)));
console.log(typeof (String(c)));
```

#### 变量.toSting()
null和undefined无toString方法

```js
console.log(typeof (a.toString()));
console.log(typeof (b.toString()));
console.log(typeof (c.toString()));
```

### 简单类型转Number
**此转换容易产生NaN，一旦被转换的变量中含有非数字字符，都容易出现NaN**

#### 变量-*/一个数字（有非数字字符会出现NaN）
JS底层做了一个强制类型转换，把字符串转换成了Number进行运算。  

```js
console.log(typeof ("10" - 5));
console.log(typeof ("10" * 5));
console.log("!@" / 5);
```

#### Number(变量)（有非数字字符会出现NaN）

```js 
console.log(typeof (Number("12312")));
console.log(typeof (Number("12312.233")));
console.log(typeof (Number(true)));
console.log(Number(true)); //1
```

#### parseInt与parseFloat
##### 空串
空字符串parseInt()和parseFloat()返回NaN，Number("")返回0;

##### parseInt(变量)
