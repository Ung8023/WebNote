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
如果变量中首个字符为字母则结果为NaN

##### 空串
空字符串parseInt()和parseFloat()返回NaN，Number("")返回0;

##### parseInt(变量)
取出现首个非数字前的整数  

```js
console.log(parseInt(true)); //NaN
console.log(parseInt("a2323")); //NaN
console.log(parseInt("23asdaw2323445")); //23
```

##### parseFloat(变量)
取出现首个非数字前的浮点数。（没有小数取整）  

```js
console.log(parseFloat(true)); //NaN
console.log(parseFloat("a2323")); //NaN
console.log(parseFloat("23asdaw2323445")); //23
console.log(parseFloat("23.2323asdaw2323445")); //23.2323
```

#### 特殊类型对应的数值

1. Boolean类型中：true数值为1；false为0；
2. null的数值类型为0；
3. undefined无数值类型或者为NaN;

### 简单类型转换成Boolean
#### 通过Boolean(变量)

```js
console.log(Boolean(12)); //true
console.log(Boolean(-1)); //true
console.log(Boolean(0)); //false
console.log(Boolean(12.23)); //true
console.log(Boolean("")); //false
console.log(Boolean("123")); // true
console.log(Boolean(NaN)); //false
console.log(Boolean(undefined)); //false
```

#### 通过 !!变量

```js
console.log(!!(12)); //true
console.log(!!(-1)); //true
console.log(!!(0)); //false
console.log(!!(12.23)); //true
console.log(!!("")); //false
console.log(!!("123")); // true
console.log(!!(NaN)); //false
console.log(!!(undefined)); //false
```