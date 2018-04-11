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

#### 借助中间对象

```js
//Worker与Person将共享同一个原型对象//不可取
Worker.prototype = Person.prototype;
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

function F() {

}

//把F的原型指向Person
F.prototype = Person.prototype;
//把Worker的原型指向一个新的F对象.F对象的原型正好指向Person.prototype
Worker.prototype = new F();

// 把PrimaryStudent原型的构造函数修复为PrimaryStudent:
Worker.prototype.constructor = Worker;

var worker = new Worker("张三", 25, 10);
worker.say();

console.log(worker.__proto__ === Worker.prototype);  //true
console.log(worker.__proto__.__proto__ === Person.prototype);  //true

console.log(worker instanceof Worker);  //true
console.log(worker instanceof Person);  //true
```

#### 封装继承操作

```js
function inHerits(Child, Parent) {
    var F = function () {};
    F.prototype = Parent.prototype;
    Child.prototype = new F();
    Child.prototype.constructor = Child;
}

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

function F() {

}

//把F的原型指向Person
F.prototype = Person.prototype;
//把Worker的原型指向一个新的F对象.F对象的原型正好指向Person.prototype
Worker.prototype = new F();

// 把PrimaryStudent原型的构造函数修复为PrimaryStudent:
Worker.prototype.constructor = Worker;

var worker = new Worker("张三", 25, 10);
worker.say();

console.log(worker.__proto__ === Worker.prototype);  //true
console.log(worker.__proto__.__proto__ === Person.prototype);  //true

console.log(worker instanceof Worker);  //true
console.log(worker instanceof Person);  //true

```