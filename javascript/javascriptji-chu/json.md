JSON是JavaScript Object Notation的缩写，它是一种数据交换格式

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