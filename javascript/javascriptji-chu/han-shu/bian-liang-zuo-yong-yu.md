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
说明JavaScript的函数在查找变量时从自身函数定义开始，从“内”向“外”查找。如果内部函数定义了与外部函数重名的变量，则内部函数的变量将“屏蔽”外部函数的变量。    

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