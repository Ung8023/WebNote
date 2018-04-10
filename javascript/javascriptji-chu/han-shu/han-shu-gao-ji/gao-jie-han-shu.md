### 什么是高阶函数
JavaScript的函数其实都指向某个变量。既然变量可以指向函数，函数的参数能接收变量，那么一个函数就可以接收另一个函数作为参数，这种函数就称之为高阶函数。

#### 高阶函数案例
编写高阶函数，就是让函数的参数能够接收别的函数。

```js
function toInt(x) {
    if(x < 0) {
        return -x;
    }else {
        return x;
    }
}

function add(x, y, f) {
    return f(x) + f(y);
}

add(-2, 5, toInt); // 7
```

### map
map方法定义在Array中，可以接受函数作为参数

```js
如果想把数组里面所有的数加1

var arr = [1, 2, 3, 4, 5, 6, 7];

function addOne(x) {
    return x + 1;
}

var anies = arr.map(addOne);
console.log(anies);
```