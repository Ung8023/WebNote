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

说明，
1. 所有的标签都可以是选择器。
2. 无论标签的层级有多深，只要都可以被选中。
3. 选择的所有，而不是一个。标签选择器，选择的是页面上所有这种类型的标签，所以经常描述“共性”，无法描述某一个元素的“个性”的。