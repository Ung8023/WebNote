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