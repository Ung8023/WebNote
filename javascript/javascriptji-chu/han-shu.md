### 函数

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