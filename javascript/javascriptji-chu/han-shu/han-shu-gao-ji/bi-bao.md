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

```js

```