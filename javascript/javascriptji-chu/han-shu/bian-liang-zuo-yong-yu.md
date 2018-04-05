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

```