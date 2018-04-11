`JavaScript`由于采用原型继承，我们无法像`Java`或`C++`直接扩展一个`Class`，因为根本不存在`Class`这种类型

### 通过Person扩展出Worker
```js
//原型链
new Worker() ----> Worker.prototype ----> Object.prototype ----> null

需要将原型变成
new Worker() ----> Worker.prototype ----> Person.prototype ----> Object.prototype ----> null
```

```js
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.say = function() {
        console.log("My name is: " + this.name + ", age is : " + this.age);
    }
}

function Worker(name, age, workAge) {
    //调用Person构造函数，绑定this
    Person.call(this, name, age);
    this.workAge = workAge;
}

var worker = new Worker("张三", 20, 2);
console.log(worker instanceof Person); //false
```

#### 