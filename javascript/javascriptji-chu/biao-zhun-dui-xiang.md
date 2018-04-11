### 各种数据的类型
用typeof操作符获取对象的类型，它总是返回一个字符串

```js
console.log(typeof 1); //number
console.log(typeof NaN); //number
console.log(typeof 'str'); //string
console.log(typeof false); //boolean
console.log(typeof undefined); //undefined
console.log(typeof alert); //function
console.log(typeof null); //object
console.log(typeof []); //object
console.log(typeof {}); //object
console.log(typeof (typeof 1)); //string
```

### 包装对象
`js`中`number`、`boolean`、`string`都有包装对象

```js
var num = new Number(123);
var bo = new Boolean(true);
var str = new String('str');

console.log(typeof num); //object
console.log(typeof bo); //object
console.log(typeof str); //object

console.log(num === 123); //false
console.log(bo === true); //false
console.log(str === 'str'); //false
```

### 注意点

* 不要使用`new Number()、new Boolean()、new String()`创建包装对象；

* 用`parseInt()`或`parseFloat()`来转换任意类型到`number；`

* 用`String()`来转换任意类型到`string`，或者直接调用某个对象的`toString()`方法；

* 通常不必把任意类型转换为`boolean`再判断，因为可以直接写`if (myVar) {...}；`

* `typeof`操作符可以判断出`number、boolean、string、function和undefined；`

* 判断`Array`要使用`Array.isArray(arr)；`

* 判断`null`请使用`myVar === null；`

* 判断某个全局变量是否存在用`typeof window.myVar === 'undefined'；`

* 函数内部判断某个变量是否存在用`typeof myVar === 'undefined'`

* `null`和`undefined`没有toString方法。

* 数字的toString，`123..toString();` 或者 `(123).toString()`