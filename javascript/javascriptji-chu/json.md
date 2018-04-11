JSON是JavaScript Object Notation的缩写，它是一种数据交换格式

我们收到一个JSON格式的字符串，只需要把它反序列化成一个JavaScript对象，就可以在JavaScript中直接使用这个对象

### JSON的数据类型
* number：和JavaScript的number完全一致；
* boolean：就是JavaScript的true或false；
* string：就是JavaScript的string；
* null：就是JavaScript的null；
* array：就是JavaScript的Array表示方式——[]；
* object：就是JavaScript的{ ... }表示方式。

### 对象字面量和Json
对象字面量定义方法和json很像，只有一点不同，json的key要求必须加“”;

```js
var obj = {a: 100};

var json = {"a": 100};
```

### json组成
`json`由`key:value` `,`以及 `{}`组成，只有一个键值对时可以没有`,`

```js
var json = {"a": 1, "b": 2, "c":3, "d":4}
```

### 序列化
```js
var car = {
    name: 'aodi',
    speed: 240,
    address: ['guangzhou', 'beijing', 'shanghai']
}

//转成JSON字符串
var s = JSON.stringify(car);
console.log(s); //{"name":"aodi","speed":240,"address":["guangzhou","beijing","shanghai"]}

//使用缩进输出
var s = JSON.stringify(car, null, ' ');
console.log(s);

{
    "name": "aodi",
    "speed": 240,
    "address": [
    "guangzhou",
    "beijing",
    "shanghai"
]
}


//第二个参数指定输出哪些参数
var s = JSON.stringify(car, ['speed', 'name'], ' ');
console.log(s);

//第二个参数可以传入转换函数
function convert(key, value) {
    if (typeof value === 'string') {
        return value.toUpperCase();
    }
    return value;
}
var s = JSON.stringify(car, convert, ' ');
console.log(s);

//精确控制如何序列化,添加toJSON()方法
var car = {
    name: 'aodi',
    speed: 240,
    address: ['guangzhou', 'beijing', 'shanghai'],
    toJSON: function() {
        return {
            'Name': this.name,
            'speed': this.speed
        }
    }
}


```