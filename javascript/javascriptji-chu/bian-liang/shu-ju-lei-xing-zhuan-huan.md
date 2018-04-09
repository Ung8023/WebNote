### 几种转换
1. 转成字符串
2. 转成数值
3. 转成布尔

### 转字符串
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

#### 通过String()

```js
console.log(typeof (String(a)));
console.log(typeof (String(b)));
console.log(typeof (String(c)));
```