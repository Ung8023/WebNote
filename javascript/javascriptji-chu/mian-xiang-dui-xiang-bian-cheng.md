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