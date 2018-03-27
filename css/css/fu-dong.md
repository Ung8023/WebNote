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
当元素浮动后，不需要转成块元素就能设置宽度高度。所有的标签都不分行内块了。一旦一个元素浮动了，那么，将能够并排了，并且能够设置宽高了。无论它原来是个div还是个span。

```css
span {
    float: left;
    width: 200px;
    height: 200px;
    background-color: orange;
}
```

#### 浮动的元素互相贴靠
```html
<style type="text/css">
    .box1 {
        width: 200px;
        height: 300px;
        float: left;
        background-color: pink;
    }

    .box2 {
        width: 200px;
        height: 150px;
        float: left;
        background-color: purple;
    }

    .box3 {
        width: 300px;
        height: 150px;
        float: left;
        background-color: orange;
    }
</style>
......
<body>
    <div class="box1"></div>
    <div class="box2"></div>
    <div class="box3"></div>
</body>
```
##### 有足够空间展示3个的宽
![](/assets/有足够空间展示3个的宽.png)
##### 宽度不够显示3个
![](/assets/宽度不够3个.png)
##### 剩余宽度不够显示长的
![](/assets/第二个下面空间不够两个.png)
