在一个对象中绑定函数，这个函数叫做对象的方法。

### 定义方法

```js
var 对象名 {
    属性名: 属性值,
    ......
    方法名: function([参数列表]) { ... }
}


var car {
    speed: 240,
    band: 'aodi',
    run: function() {
        console.log("车跑了");
    }
}

car.run();
```

### this
在一个方法内部，`this`是一个特殊变量，它始终指向当前对象，也就是`car`这个变量。