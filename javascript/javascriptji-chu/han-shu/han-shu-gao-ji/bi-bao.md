### 函数作为返回值
```js
function add () {
    console.log("add");
}

function getAdd() {
    return add;
}

var f = getAdd();
f();

function getAdd2() {
    return function () {
        console.log("add2");
    }
}
f = getAdd2(); //调用getAdd2()；返回的是一个函数，并不会执行里面的语句；
f();
```

### 闭包
返回的函数引用了变量`i`，但它并非立刻执行。等到3个函数都返回时，它们所引用的变量`i`已经变成了`4`，因此最终结果为`16`
返回闭包时牢记的一点就是：返回函数不要引用任何循环变量，或者后续会发生变化的变量。

```js
function newArray() {
    var arr = [];
    for (var i = 1; i<=3; i ++) {
        arr.push(function () {
            return i * i;
        });
    }

    return arr;
}


var arr = newArray();
var f1 = arr[0];
var f2 = arr[1];
var f3 = arr[3];

f1(); //16
f2(); //16
f3(); //16
```

#### 在循环中使用闭包
