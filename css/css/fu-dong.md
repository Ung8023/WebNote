使元素脱离标准流的方式之一。

### 使盒子并排显示
效果：  

![](/assets/浮动并排显示.png)

代码：  

```html
<style type="text/css">
    .box1 {
        float: left;
        width: 200px;
        height: 300px;
        background-color: blue;
    }

    .box2 {
        float: left;
        width: 500px;
        height: 300px;
        background-color: green;
    }
</style>
......
<body>
    <div class="box1"></div>
    <div class="box2"></div>
</body>
```

**两个元素并排了，并且两个元素都能够设置宽度、高度了（这在刚才的标准流中，不能实现）。**

### 浮动的三个性质:
1. 浮动的元素脱离标准流
2. 浮动的元素互相贴靠
3. 浮动的元素有“字围”效果

#### 浮动的元素脱离标准流
