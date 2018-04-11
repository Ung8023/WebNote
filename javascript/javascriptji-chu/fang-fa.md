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

```js
function getSpeed() {
    console.log(this.speed);
    return this.speed;
}

var car = {
    speed: 240,
    band: 'aodi',
    run: getSpeed
}

car.run(); // 240
getSpeed(); // undefined
```

#### this指向
1. this只出现在函数中。
2. 谁调用函数，this就指的是谁。
3. new People();   People中的this代指被创建的对象实例。

##### this指向错误
```js
var car = {
    speed: 240,
    band: 'aodi',
    run: function () {
        console.log("速度是：" + this.speed);
    }
}
var f = car.run;
f(); // 错误，必须通过obj.fun(),调用


var car = {
    speed: 240,
    band: 'aodi',
    run: function () {
        
    }
}

```