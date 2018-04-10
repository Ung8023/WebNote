### 箭头函数
ES6开始支持  
使用箭头的方式定义函数，也就是通常所说的Lambda表达式

### 语法
```js
(x1, x2, ...) => { 函数体; return 返回值; }

如果函数体只有一行

(x1, x2, ...) => 表达式;


(x, y) => x + y;
//相当于
function(x, y) {
    return x + y;
}

//无参数
() => 1;

//可变参数
(x, y, ...rest) => {
    ......
}
```

#### 返回一个对象
```
x => {a: x}  // 语法错误，因为{}与函数体有冲突

x => ({a:x}) // 使用此种方法替代。
```

### this
箭头函数看上去是匿名函数的一种简写，但实际上，箭头函数和匿名函数有个明显的区别：箭头函数内部的`this`是词法作用域，由上下文确定。

```js
var obj = {
    birth: 1990,
    getAge: function () {
        var b = this.birth; // 1990
        var fn = function () {
            return new Date().getFullYear() - this.birth; // this指向window或undefined
        };
        return fn();
    }
};

//现在，箭头函数完全修复了this的指向，this总是指向词法作用域，也就是外层调用者obj：
var obj = {
    birth: 1990,
    getAge: function () {
        var b = this.birth; // 1990
        var fn = () => new Date().getFullYear() - this.birth; // this指向obj对象
        return fn();
    }
};
obj.getAge(); // 25
```