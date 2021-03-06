## 分支语句
### if语句
#### 基本语法
```js
if(条件表达式) {
    ......
} else {
    ......
}
```  


```js
if(条件表达式1){	
    ......
}else if(条件表达式2){	
    ......
}else if(条件表达式3){	
    ......
}else{	
    ......
}
```

#### if语句嵌套
```js
if(满足条件) {
    if(条件1) {
        ......
    } else if(条件2) {
        ......
    } else {
        ......
    }
}
```

#### 三目运算符

```js
表达式1？值1：值2

var a= 10;
var b = a == 12 ? 2 : 1;  

```

### switch语句
#### 基本语法
```js
switch (a) {
    case 1 :
        
        break;
    case 2:
        
        break;
    case 12:
        
        break;
    default:
        break;
}
```

#### 注意点
1. break可以省略；如果省略，代码会继续执行下一个case
2. 语句在比较值时使用的是全等操作符，因此不会发生类型转换

## 循环语句
### for循环语句
#### 基本语法
```js
for (变量;条件1;条件2) {
    ......
} 
```

```js
for (int i=0; i < 100; i++) {
    document.write(i);
}
```

#### 执行过程

```js
变量->条件1->执行程序->条件2->条件1->执行程序.....直到条件1不成立，跳出循环。
```

#### 死循环

```js
for(;;){程序}
```

### while循环语句
#### 基本语法

```js
while(条件) {
    语句;
}

var a = 1;
var sum = 0;
while(a < 100) {
    sum += a;
    a ++;
}
```

#### 死循环

```js
while(true) {
    语句;
}
```

#### do...while循环（一定会执行一次do中的程序)

```js
do{
    语句;
}while(条件);

var a = 1;
var sum = 0;
do {
    sum += a;
    a ++;
}while(a < 100);
```

### break与continue

1. break     :  立刻跳出循环，不在执行该循环中的任何程序；
2. continue  :  跳出本次循环，进入下一次循环中继续执行程序；  

```js
输出1-100所有偶数

//第1种实现
function a1() {
    for (var a = 1; a <= 100; a ++) {
        if (a % 2 == 1) {
            continue;
        }else {
            console.log(a);
        }
    }
}

//第2种实现
function a2() {
    for (var a = 1; a <= 100; ) {
        if (a % 2 == 0) {
            console.log(a);
        }
        a ++;
    }
}

//第3种实现
function a3() {
    var a = 1;
    for (; a <= 100; ) {
        if (a % 2 == 0) {
            console.log(a);
        }
        a ++;
    }
}

//第4种实现
function a4() {
    var a = 1;
    while ( a <= 100) {
        if (a % 2 == 0) {
            console.log(a);
        }
        a ++;
    }
}

//第5种实现
function a5() {
    var a = 1;
    do {
        if (a % 2 == 0) {
            console.log(a);
        }
        a ++;
    } while ( a <= 100);
}

```