JavaScript不区分类和实例的概念，而是通过原型（prototype）来实现面向对象编程。

### 定义一个Object

```js
var Person = {
    name: 'person',
    age: 0,
    say: function() {
        console.log('say');
    }
}
```

### 创建一个具体的person
在编写`JavaScript`代码时，不要直接用`obj.__proto__`去改变一个对象的原型，并且，低版本的IE也无法使用`__proto__`  

```js
var Person = {
    name: 'person',
    age: 0,
    say: function() {
        console.log('say');
    }
}

var p1 = {
    name: 'p1',
    age :20
}

p1.__proto__ = Person;
console.log(p1.name);
console.log(p1.age);
p1.say();
```

### 创建一个具体的Person
`Object.create()`方法可以传入一个原型对象，并创建一个基于该原型的新对象，但是新对象什么属性都没有

```js
var Person = {
    name: 'person',
    age: 0,
    say: function() {
        console.log('say:' + this.age);
    }
}

var p1 = {
    name: 'p1',
    age :20
}

var pa = Object.create(Person);
pa.name = 'pa';
pa.age = 20;
pa.say();
```