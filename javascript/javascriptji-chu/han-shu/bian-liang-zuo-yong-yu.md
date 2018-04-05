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

