### 原型调用链
当我们用`obj.xxx`访问一个对象的属性时，`JavaScript`引擎先在当前对象上查找该属性，如果没有找到，就到其原型对象上找，如果还没有找到，就一直上溯到`Object.prototype`对象，最后，如果还没有找到，就只能返回`undefined`

```js
普通对象调用链
对象.xxx ==>  对象 -> 继承.prototype -> Object.prototype --> null

数组调用链
arr ----> Array.prototype ----> Object.prototype ----> null

函数调用链
foo ----> Function.prototype ----> Object.prototype ----> null
```

### 构造函数
定义对象可以通过`{..}`,也可以通过构造函数
#### 定义构造函数
```js
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.say = function() {
        console.log("My name is: " + this.name + ", age is : " + this.age);
    }
}

var p1 = new Person("张三", 20);
p1.say();
```