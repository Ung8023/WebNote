### 数学运算符
比如要计算:  

![](/assets/计算这个数学表达式.png)  

在js中就是`(3 + 4 * 5)/(6 + 3);`

#### 数学运算符

| 符号 | 含义 |
| :---: | :---: |
| +  | 加 |
| - | 减 | 
| * | 乘 |
| / | 除 |
| % | 取余数 |
| () | 括号 |

##### 计算顺序
1. 先算乘除，后算加减
2. 先算括号里的，没有大括号，小括号可以嵌套
3. 乘、除、取余数的运算优先级相同，谁写在前面，先算谁。

#### 乘方和开根号
##### 乘方
计算3<sup>4</sup> :  

```js
var a = Math.pow(3, 4);
```  

计算 3<sup>4*5</sup> :  

```js
var a = Math.pow(3, 4*5);
```

##### 开根号
计算 `√81` :   

```js
var a = Math.sqrt(81);
```

### 变量格式转换
#### 字符串转数字
```js
parseInt("5");
parseInt("123的衣阿华圣诞节卡号123123");//123,后面的中文自动消失，只保留最开头的数字
parseInt(5.5 + 4.8); // 10 自动取整
```

### 关系运算符 
关系运算符，得到的结果都是布尔值，也就是说得到的东西要么是true，要么是false  

| 运算符 | 含义 |
| :---: | :--- |
| >	 | 大于号 |
| <	 | 小于号 |
| >= 	 | 大于或等于 |
| <=   | 小于或等于 |
| == 	 | 等于 |
| ===  | 全等于 |
| !=	 | 不等于 |
| !==  | 不全等于 |
 
```js
document.write(6 < 10 );
document.write("<br>");
document.write(6 < 1 );
document.write("<br>");
document.write(6 == 6 );
document.write("<br>");
document.write(6 != 6 );
```

### 逻辑运算符
参与逻辑运算的，都是布尔值。也就是说，只有true、false才能参与逻辑运算，得到的答案，仍然是布尔值。

| 运算符 | 含义 |
| :---: | :--- |
| &&	 | 与(且) |
| \|\|	 | 或 |
| ! 	 | 非 |


### 运算符优先级
1. ()
2. !、-（负数）、++、-- （正数省略+）（一元运算）
3. *、/、% 
4. +、- （加，减）（二元运算）
5. <、<=、<、>= （一级逻辑运算）
6. ==、!=、===、!==、 （二级逻辑运算）
7. && （三级级逻辑运算）
8. || 
9. ?: （三元运算）
10. =、+=、-=、*=、/=、%= （赋值运算）
