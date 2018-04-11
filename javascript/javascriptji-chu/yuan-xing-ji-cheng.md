`JavaScript`由于采用原型继承，我们无法像`Java`或`C++`直接扩展一个`Class`，因为根本不存在`Class`这种类型

### 通过Person扩展出Worker

```js
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.say = function() {
        console.log("My name is: " + this.name + ", age is : " + this.age);
    }
}


```