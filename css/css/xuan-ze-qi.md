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

### 基础选择器
#### 标签选择器
就是标签的名字  

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
</style>
......
 <p class="param2"> 这是定义了class的标签 </p>
```



##### 一个标签可以被多个选择器选中
标签选择器和id选择器都选中了id为param的标签，会共同作用

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
