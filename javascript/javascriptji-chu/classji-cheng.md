`class`从ES6开始正式被引入到`JavaScript`中。使定义类更加简单。

### 新旧方式对比
```js
//旧方式
function Person(name) {
    this.name = name;
}

//为了使创建出的对象使用同一个函数
Person.prototype.say = function () {
    console.log("My name is " + this.name);
}

class Person {
    constructor(name) {
        this.name = name;
    }

    say() {
        console.log("My name is " + this.name);
    }
}

```