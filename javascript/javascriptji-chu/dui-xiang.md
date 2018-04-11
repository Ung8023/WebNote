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
    'pro-address': 'guangzhou'
}
```

#### 属性使用
通过`对象.属性`来获取属性对应的值

