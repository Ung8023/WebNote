### 什么是对象
JavaScript的对象是一种无序的集合数据类型，它由若干键值对组成。

### 定义对象
用一个`{...}`表示一个对象，键值对以`xxx: xxx`形式申明，用,隔开。注意，最后一个键值对不需要在末尾加,

```
var 对象 = {
    属性: 值,
    ......
    属性: 值
}

........

var car = {
    band: 'aodi',
    speed: 240,
    //属性名必须为一个有效的变量名，如果属性名包含特殊字符，就必须用''括起来
    'pro-address': 'guangzhou'
}
```

#### 属性使用
通过`对象.属性`来获取属性对应的值

```js
car.speed; //240
car.band;  //'aodi'
//有效变量名，也可以使用此方式访问
car['band']; //'aodi'
//不是一个有效的变量，就需要用''括起来。访问这个属性也无法使用.操作符，必须用['xxx']来访问
car['pro-address']; // 'guangzhou' 
//访问不存在的属性
car.name; // undefined
```

#### 属性操作

##### 新增一个属性
对象.新属性名 = 新属性值;

```js
新增一个属性

car.pro_date = 'xxxx';
console.log(car.pro_date); //xxxx
```

##### 删除一个属性
delete 对象.属性名

```js
删除一个属性
delete car.speed;
console.log(car.speed); //undefined
```

##### 判断对象时候有某个属性
'属性名' in 对象

```js
'speed' in car; // true;
'name' in car; // false
```

