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


```