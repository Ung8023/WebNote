### 匿名函数
没有名字的函数

1. 不需要定义函数名的时候使用
2. 书写起来更方便

#### 三种调用方式
1. 直接调用或者自调用；
2. 事件绑定
3. 定时器

##### 直接调用或自调用

```js
(function() {
    console.log("调用");
})();
```

##### 事件绑定

```js
btn.onclick = function () {
    console.log("按钮点击了");        
}
```

### 函数是一种类型

```js
function fun() {
    console.log("fun");
}

function fun1() {
    console.log("fun");
}

console.log(typeof fun); //function
console.log(typeof fun1); //function
```

### 函数作为参数传递

```js
function add(c) {
    console.log(c);
}

function log(a) {
    a(1);
}

log(add);
```

### 递归
就是函数自己调用自己，但必须有跳出条件，不然会出现死循环。

```js

```