### 局部变量
#### 函数内部声明
如果一个变量在函数体内部申明，则该变量的作用域为整个函数体，在函数体外不可引用该变量  

```js
'use strict'

function func() {
    var a = 0;
    a = 12;
}

a = 20; //Uncaught ReferenceError: a is not defined
console.log(a);
func();
```

#### 不同函数中的同名变量互不影响

```js
'use strict'
function a() {
    var b = 10;
    b = 20;
    console.log(b);
}

function b() {
    var b = 'x';
    console.log(b);
}
```

#### 内部函数可以访问外部函数定义的变量
内部函数可以访问外部函数定义的变量,但是外部函数不能访问内部函数的变量

```js
'use strict'
function a() {
    var a = 10;

    function b() {
        a = 20;
        console.log(a)
    }
    b();
}
a();
```

##### 内部函数和外部函数变量重名
说明JavaScript的函数在查找变量时从自身函数定义开始，  
从“内”向“外”查找。如果内部函数定义了与外部函数重名的变量，则内部函数的变量将“屏蔽”外部函数的变量。    

```js
'use strict'
function a() {
    var a = 10;
    var c = 100;

    function b() {
        a = 20;
        var c = 'bbbb';
        console.log(a);
        console.log(c);
    }
    b();
    console.log(c);
}
a();
```

### 变量提升
JavaScript的函数定义有个特点，它会先扫描整个函数体的语句，把所有申明的变量“提升”到函数顶部
在函数体内部，声明变量，会把该声明提升到函数体的最顶端。 只提升变量声明，不赋值。

```js
function a() {
    console.log(num);
    var name = 20;
}
.......
//等价于
function a() {
    var num;
    console.log(num);
    num = 20;
}

```

#### 局部作用域
由于JavaScript的变量作用域实际上是函数内部，在for循环等语句块中是无法定义具有局部作用域的变量  

```js
'use strict';

function circle() {
    for (var i=0; i<100; i++) {
        //
    }
    i += 100; // 仍然可以引用变量i
}
```

##### ES6 使用let关键字声明一个块级作用域变量

```js
'use strict';

function circle() {
    for (let i=0; i<100; i++) {
        //
    }
    i += 100; // 不可以使用
}

```

### 全局变量
不在任何函数内定义的变量就具有全局作用域。实际上，JavaScript默认有一个全局对象window，全局作用域的变量实际上被绑定到window的一个属性。

```js
'use strict';
var str = "this is a String";
alert(str);
alert(window.str);
```

#### 顶层函数也为全局变量

```js
function func() {
    alert("func");
}

func();
window.func();
```

### 常量
#### ES6之前做法
用全部大写的变量来表示一个常量

```js
var PI = 3.14;
```

#### ES6使用const关键字

```js
'use strict';

const PI = 3.14;
PI = 3; //某些浏览器不报错，但是无效果！
```

### 解构赋值
#### 对数组的解构赋值
对数组元素进行解构赋值时，多个变量要用[...]括起来

```js
var array = ['aaaa', 'bbbb', 'cccc'];
var [a, b, c] = array;
console.log(a);
console.log(b);
console.log(c);

.......
//等价于

var a = array[0];
var b = array[1];
var c = array[2];
```

##### 嵌套数组的解构
嵌套层次和位置要保持一致

```js
var array = ['aaa', ['bbb', 'ccc'], 'ddd'];
var [a, [b, c], d] = array;
console.log(a);
console.log(b);
console.log(c);
console.log(d);
```  

##### 忽略某些元素

```js
var array = ['aaa', ['bbb', 'ccc'], 'ddd'];
var [, [, c], d] = array;
console.log(c); // ccc
console.log(d); // ddd
```

#### 对对象解构
对对象解构时，变量名要和对象中的名称一样。  
如果对应的属性不存在，变量将被赋值为undefined

```js
var car = {
    name: 'aodi',
    speed: 120,
    color: 'red'
};

var {name, speed, color} = car;
console.log("name = " + name + ", speed = " + speed + "color = " + color);
```

#### 解构对象使用变量名与属性名不同时写法
`var{ 对象属性名:变量名, 对象属性名:变量名 ...... }`

```js
var {name:a, speed:b } = car;
console.log("name = " + a + ", speed = " + b + "color = " + color);
```

#### 解构嵌套对象

```js
var car = {
        name: 'aodi',
        speed: {
            max: 240,
            acc: 50
        },
        color: 'red'
    };

    var {name ,speed:{max, acc}} = car;

    console.log("name = " + name + ", maxSpeed = " + max + ", acc = " + acc);
```