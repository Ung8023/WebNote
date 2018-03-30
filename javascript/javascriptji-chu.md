### js构成

1. 语言核心
2. DOM编程
3. BOM编程

### ECMAScript

ECMAScript不是一门语言，而是一个标准。符合这个标准的比较常见的有：JavaScript、Action Script（Flash中用的语言）。

### 程序书写位置

`<script>`标签既可以出现在`head`中，也可以出现在`body`中。

#### 在页面内写script标签对中写

```html
<script type="text/javascript">
    书写javascript代码
</script>
```

#### 外部js引入

```html
<script src="myScript.js"></script>
```

#### alert语句

```js
alert("今天天气很好呀");
```

### 语法规则：
1. js对换行、缩进、空格不敏感。
2. 每一条语句末尾最好加上分号(不是必须)，但是为了避免压缩程序出现问题，最好都加。
3. 所有的符号都是英文的。比如：引号、分号、括号...。
4. script标签书写要正确。

### 注释
```js
// 单行注释
alert("hello");
/*
    这是一个多行注释
    这是一个多行注释
    这是一个多行注释
*/
alert("yes it is");
```

### 字面量(直接量)
“直接量”也称为“字面量”，就是看见什么，它就是什么。简单的直接量有2种：数字、字符串。

#### 数字
```js
alert(456);
```

#### 字符串
单词、句子，它们不是数字。一定要加上引号。  

```js
alert("Hello");
```

### console
console表示“控制台”