### 函数

### 什么是函数

定义的可以重复执行的代码块

### 为什么使用函数

1. 将重复性极高，功能统一的代码，集成为一个函数，形成模块，去除了冗余，使代码更清晰
2. 维护更方便，相当于针对模块编程
3. 一处定义，多模块使用，甚至多项目使用，复用性极高

### 定义函数的基本语法

```js
function 函数名(x1, x2, x3...) {
    函数体
    return m;
}
```

1. `function` 用来指出这是一个函数的关键字。
2. `函数名` 是函数的名称
3. `(x1, x2 ...)` 是函数的参数列表，可以为0 个或者多个，多个参数以`,`分割
4. `{}` 之间是函数体，可以包含若干语句或者没有语句。
5. `return m;` 函数执行完毕返回的值。一旦执行到return，函数就执行完毕，并将结果返回

#### 参数
设置参数曾强了函数的功能性，和程序员的交互性，和函数的可拓展性。

##### 形参
形式上参与运算的变量，无实际值，为实参占位置

##### 实参
实际参与运算的变量。形参为他占位置，真实参与运算的变量。

##### 返回值
函数程序运行后的结果外部需要使用的时候，我们不能直接给与，需要通过return返回。

总结：函数内部，return后面的值就是返回值；

作用：函数执行后剩下结果就是返回值。

###### 注意点
1. 如果函数没有显示的使用 return语句 ，那么函数有默认的返回值：undefined
2. 如果函数使用 return语句，那么跟再return后面的值，就成了函数的返回值
3. 如果函数使用 return语句，但是return后面没有任何值，那么函数的返回值	也是：undefined
4. 函数使用return语句后，这个函数会在执行完 return 语句之后停止并立即退	出，也就是说return后面的所有其他代码都不会再执行

### 函数的定义方法
#### 通过function关键字创建

```js
function fun() {
    alert("函数被调用了");
}

fun();
```

#### 通过函数直接量声明

```js
var fun = function() {
   alert("函数被调用了"); 
}

fun();
```

#### 通过Function声明

```js
var func = new Function("
    var a =10;
    var b =20;
    alert(a + b);
");

func();
```

### 调用函数

```js
function add(x1, x2) {
    return x1 + x2;
}
```

#### 正常调用

```js
函数名(参数1, 参数2, 参数3 ....);

func();
add(12, 23)
```

#### 传入比正常参数多的
由于JavaScript允许传入任意个参数而不影响调用，因此传入的参数比定义的参数多也没有问题，虽然函数内部并不需要这些参数  

```
add(10, 20, 2, 3, 4, 5) // 结果是30
```

#### 传入参数比定义的少

```js
add(); // 返回NaN
add(12); // 返回NaN
```

### arguments
只在函数内部起作用，永远指向当前函数的调用者传入的所有参数。   
arguments对象的长度是由实参个数而不是形参个数决定的  
`arguments`类似`Array`但它不是一个`Array`  

```
function add() {
    var sum = 0;
    for (var i = 0; i< arguments.length; i ++) {
        sum += arguments[i];
    }
    console.log(sum);
}

add(12, 23, 23, 434, 54);
```

#### arguments用途
1. 用于判断传入参数的个数
2. 中间的参数b变为“可选”参数，就只能通过arguments判断，然后重新调整参数并赋值。

    ```js
    // foo(a[, b], c)
    // 接收2~3个参数，b是可选参数，如果只传2个参数，b默认为null：
    function foo(a, b, c) {
        if (arguments.length === 2) {
            // 实际拿到的参数是a和b，c为undefined
            c = b; // 把b赋给c
            b = null; // b变为默认值
        }
        // ...
    }
    ```
    
### rest参数
由于JavaScript函数允许接收任意个参数，于是我们就不得不用arguments来获取所有参数
#### 普通写法

```js
function foo(a) {
    var i, rest = [];
    if (arguments.length > 1) {
        for (i = 1; i < arguments.length; i ++) {
            rest.push(arguments[i]);
        }
    }
    console.log("a = " + a);
    console.log(rest);
}
```

#### ES6写法
ES6标准引入了rest参数

```js
function foo(a, ...rest) {
    console.log('a = ' + a);
    console.log(rest);
}
```