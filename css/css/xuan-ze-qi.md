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

id选择器的选择符是“#”，需要先给标签指定id属性

##### html标签id名字取值规则
1. 只能有字母数字下划线
2. 必须以字母开头
3. 不能和标签同名，比如id不能为body、p、span

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

##### 特点
1. 任何标签都可以携带class属性，class属性可以重复，比如，页面上可能有很多标签都有`param2`这个类
2. 同一个标签，可能同时属于多个类，用空格隔开

    ```html
    <p class="param2 param1"> 这也是定义了class的标签 </p>
    ```
##### 使用技巧
1. 不要去试图用一个类名，把某个标签的所有样式写完。这个标签要多携带几个类，共同造成这个标签的样式。
2. 每一个类要尽可能小，有“公共”的概念，能够让更多的标签使用。
3. 尽可能的用class，除非极特殊的情况可以用id。

    ```
    id是js用的。也就是说，js要通过id属性得到标签，
    所以我们css层面尽量不用id，要不然js就很别扭。
    另一层面，我们会认为一个有id的元素，有动态效果。
    ```

### 一个标签可以被多个选择器选中
标签选择器和id选择器都选中了id为param的标签，会共同作用,就是一个标签，可以同时被多种选择器选择，标签选择器、id选择器、类选择器。这些选择器都可以选择上同一个标签，从而影响样式，这就是css的cascading“层叠式”的第一层含义。

```
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
语法：  
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
后代选择器，描述的是祖先结构。后代选择器选择的是后代，而不是单纯的儿子。空格可以多次出现。当要把某一个部分的所有的什么，进行样式改变，就要想到后代选择器。

#### 交集选择器

