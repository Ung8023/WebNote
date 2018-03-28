选择器是用来选中html中的标签。

### 什么是选择器？

```html
<style type="text/css">
/* 在此处书写css代码 */
p {
background-color: antiquewhite;
}

h1 {
background-color: antiquewhite;
}

</style>
```

在整个{}之前写的就是选择器，比如p和h1 都是选择器。选择器有很多种。  
先写选择器，然后写大括号，大括号里面是样式。

### 基础选择器

#### 标签选择器

就是用标签名来当做选择器。  
1） 所有标签都能够当做选择器，比如body、h1、dl、ul、span等等  
2） 不管这个标签藏的多深，都能够被选择上。  
3） 选择的是所有的，而不是某一个。所以是共性，而不是特性。

```html
<style type="text/css">

    span{
        color:red;
    }
</style>
...
<p>这里是一个<span>段落</span></p>
```

**说明：**

1. 所有的标签都可以是选择器。
2. 无论标签的层级有多深，只要都可以被选中。
3. 选择的所有，而不是一个。
4. 标签选择器，选择的是页面上所有这种类型的标签，所以经常描述“共性”，无法描述某一个元素的“个性”的。

#### id选择器

`#`表示选择id

```html
<style type="text/css">

    #para2{
        color:red;
    }
</style>

......
<p>我是段落1</p>

<p id="para2">我是段落2</p>
<p>我是段落3</p>
```

id选择器的选择符是“\#”，需要先给标签指定id属性

##### html标签id名字取值规则

1. 只能有字母数字下划线
2. 必须以字母开头
3. 不能和标签同名，比如id不能为body、p、span

任何的标签都可以有id，id的命名要以字母开头，可以有数字、下划线。大小写严格区别，也就是说mm和MM是两个不同的id。

**一个Html页面不能出现相同id，哪怕他们不是一个类型。比如页面上有一个id为pp的p，一个id为pp的div，是非法的！**

#### 类选择器

语法: `.类名{ key:value; }`

```html
<style type="text/css">
    .param2{
        font-size: 16px;
    }
    .param1{
        color:red;
    }
</style>
......
 <p class="param2"> 这是定义了class的标签 </p>
 <p class="param2"> 这也是定义了class的标签 </p>
```

一些基础类名：

| 功能 | 类名 |
| :---: | :---: |
| 头 | header |
| 内容 | content/container |
| 尾 | footer |
| 导航 | nav |
| 侧栏 | sidebar |
| 栏目 | column |
| 页面外围控制整体布局宽度 | wrapper |
| 左右中 | left right center |
| 登录条 | loginbar |
| 标记 | logo |
| 广告 | banner |
| 页面主体 | main |
| 热点 | hot |
| 新闻 | news |
| 下载 | download |
| 子导航 | subnav |
| 菜单 | menu |
| 子菜单 | submenu |
| 搜索 | search |
| 友情链接 | friendlink |
| 页脚 | footer |
| 版权 | copyright |
| 滚动 | scroll |

##### 特点

1. 任何标签都可以携带class属性，class属性可以重复，比如，页面上可能有很多标签都有`param2`这个类
2. 同一个标签，可能同时属于多个类，用空格隔开

   ```html
    <p class="param2 param1"> 这也是定义了class的标签 </p>
   ```

3. 在css中使用`.`来表示类

##### 使用技巧

1. 不要去试图用一个类名，把某个标签的所有样式写完。这个标签要多携带几个类，共同造成这个标签的样式。
2. 每一个类要尽可能小，有“公共”的概念，能够让更多的标签使用。
3. 每个标签，选取自己想要的类
4. 尽可能的用class，除非极特殊的情况可以用id。

   ```
    id是js用的。也就是说，js要通过id属性得到标签，
    所以我们css层面尽量不用id，要不然js就很别扭。
    另一层面，我们会认为一个有id的元素，有动态效果。
   ```

### 一个标签可以被多个选择器选中

标签选择器和id选择器都选中了id为param的标签，会共同作用,就是一个标签，可以同时被多种选择器选择，标签选择器、id选择器、类选择器。这些选择器都可以选择上同一个标签，从而影响样式，这就是css的cascading“层叠式”的第一层含义。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style type="text/css">
        /* 在此处书写css代码 */
        p {
            background-color: antiquewhite;
            font-weight: bold;
            font-style: italic;
            text-decoration: underline;
        }

        #param1 {
            color: #eee;
        }
    </style>
</head>
<body>
    <p>这里是一个段落</p>
    <p id="param1"> 这是另一个段落</p>
</body>
</html>
```

### 高级选择器

#### 后代选择器

语法\(使用空格表示后代关系\)：

```
选择器1 选择器2 选择器3 ... {

}
```

```html
<html>
<head>
    <meta charset="UTF-8">
    <title>后代选择器</title>
    <style type="text/css">
        .div1 p {
            color: red;
        }
    </style>
</head>
<body>
    <div class="div1">
        <ul>
            <li>
                <p>段落1</p>
                <p>段落2</p>
                <p>段落3</p>
            </li>
        </ul>
    </div>
</body>
</html>
```

##### 说明

后代选择器，描述的是祖先结构。  
后代选择器选择的是后代，而不是单纯的儿子。  
空格可以多次出现。当要把某一个部分的所有的什么，进行样式改变，就要想到后代选择器。

#### 交集选择器

选择的元素是同时满足两个条件：必须是h3标签，然后必须是sp标签。  
交集选择器没有空格。一般都是以标签名开头，比如div.haha

```css
h3.sp{
    color:red;
}
```

##### 交集选择器连续交（一般不推荐使用）

IE7开始兼容，IE6不兼容。

```css
h3.special.zhongyao{
    color:red;
}
```

#### 并集选择器

用逗号就表示并集

```css
p, li {
    color: red;
}
```

#### 通配符选择器

`*` 代表所有元素，效率不高，如果页面上的标签越多，效率越低，所以页面上不能出现这个选择器。

```css
* {
    color: red;
}
```

### 一些CSS3选择器

#### 儿子选择器\(IE7开始兼容，IE6不兼容\)

`div>p`选择div的儿子p，与div的后代p不同，后代选择器能选中li中的p。

```html
div>p {
    color: red;
}
......
<div>
    <ul>
        <li>
            <p>这是一个啥</p>
        </li>
    </ul>
    <p>这是一个啥</p>
</div>
```

#### 序选择器\(IE8兼容，IE6、7不兼容\)

通过`:`指定第几个

```html
ul li:first-child {
    color: red;
}

ul li:last-child {
    color: green;
}
```

如果要求兼容IE6、7，就需要自己定义类名，用类选择器来选择第一个或最后一个:

```html
ul li.first {
    color: red;
}

ul li.last {
    color: green;
}
......
<ul>
    <li class="first">asf</li>
    <li>asf</li>
    <li>asf</li>
    <li>asf</li>
    <li>asf</li>
    <li class="last">asf</li>
</ul>
```

#### 下一个兄弟选择器

"+"表示下一个兄弟

```css
h3+p {
    color: red;
}
```

选中的是紧挨在h3标签后面的第一个兄弟。

