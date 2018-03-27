使元素脱离标准流的方式之一。遵循一个原则：永远不是一个东西单独浮动，浮动都是一起浮动，要浮动，大家都浮动。

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
4. 浮动元素不设置宽度会收缩为文字宽度

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

#### 浮动的元素有“字围”效果
div挡住了p，但是p中的文字不会被挡住，形成“字围”效果。  

```html
<style type="text/css">
    div {
        float: left;
    }
</style>
......
<div><img src="1.jpg" alt=""></div>
<p>啊发发发沙发上看风景奥斯卡了房间奥斯卡了房间按时发顺丰看
    见爱上咖啡机昂克赛拉附加阿卡丽暗示法法师爱的好久阿发
    阿法发顺丰按时发附件阿双方将阿喀琉斯啊阿双方科技阿卡丽啊
    阿发饭卡三角阀看来是
</p>
```

**让div浮动，p不浮动. div挡住了p，但是p中的文字不会被挡住，形成“字围”效果。**

![](/assets/浮动元素字围效果.png)

#### 浮动元素不设置宽度会收缩为文字宽度
一个浮动的元素，如果没有设置width，那么将自动收缩为文字的宽度（这点非常像行内元素）  

```html
<style type="text/css">
    div{
        float: left;
        background-color: gold;
    }	
</style>
```

### 清除浮动
不清除浮动的效果:  

![](/assets/不清除浮动的效果.png)

原因：   

    第二个div中的li，去贴第一个div中最后一个li的边了。原因就是因为div没有高度，不能给自己浮动的孩子们，一个容器。
   
```html
<style type="text/css">
    li {
        float: left;
        width: 90px;
        height: 40px;
        background-color: gold;
        text-align: center;
    }
</style>
......
<div>
    <ul>
        <li>第1个li</li>
        <li>第2个li</li>
        <li>第3个li</li>
        <li>第4个li</li>
        <li>第5个li</li>
    </ul>
</div>

<div>
    <ul>
        <li>第01个li</li>
        <li>第02个li</li>
        <li>第03个li</li>
        <li>第04个li</li>
        <li>第05个li</li>
    </ul>
</div>
```

#### 清除浮动1: 给浮动元素的祖先元素加高度(很少使用)。
如果一个元素要浮动，那么它的祖![先元素一定要有高度。**有高度的盒子，才能关住浮动。**](/assets/通过设置高度清除影响后.png)

只要浮动在一个有高度的盒子中，那么这个浮动就不会影响后面的浮动元素。所以就是清除浮动带来的影响了。

```html
<style type="text/css">
    li {
        float: left;
        width: 90px;
        height: 40px;
        background-color: gold;
        text-align: center;
    }

    div {
        height: 40px;
    }
</style>
......
<div>
    <ul>
        <li>第1个li</li>
        <li>第2个li</li>
        <li>第3个li</li>
        <li>第4个li</li>
        <li>第5个li</li>
    </ul>
</div>

<div>
    <ul>
        <li>第01个li</li>
        <li>第02个li</li>
        <li>第03个li</li>
        <li>第04个li</li>
        <li>第05个li</li>
    </ul>
</div>
```

清除浮动影响后：  

![](/assets/通过设置高度清除影响后.png)


#### 清除浮动2：`clear:both`
clear就是清除，both指的是左浮动、右浮动都要清除。意思就是：清除别人对我的影响。**这种方法有一个非常大的、致命的问题，margin失效了。**

```html
<style type="text/css">
    li {
        float: left;
        width: 90px;
        height: 40px;
        background-color: gold;
        text-align: center;
    }

    .div2 {
        margin-top: 10px;
        clear: both;
    }

</style>
......
<div>
    <ul>
        <li>第1个li</li>
        <li>第2个li</li>
        <li>第3个li</li>
        <li>第4个li</li>
        <li>第5个li</li>
    </ul>
</div>

<div class="div2">
    <ul >
        <li>第01个li</li>
        <li>第02个li</li>
        <li>第03个li</li>
        <li>第04个li</li>
        <li>第05个li</li>
    </ul>
</div>
```

#### 清除浮动3: 隔墙法
```html
<style type="text/css">
    li {
        float: left;
        width: 90px;
        height: 40px;
        background-color: gold;
        text-align: center;
    }

    .cl {
        clear: both;
    }

    div.wall {
        height: 1px;
    }
</style>
......
<div>
    <ul>
        <li>第1个li</li>
        <li>第2个li</li>
        <li>第3个li</li>
        <li>第4个li</li>
        <li>第5个li</li>
    </ul>
</div>
<div class="wall cl"></div>
<div class="div2">
    <ul >
        <li>第01个li</li>
        <li>第02个li</li>
        <li>第03个li</li>
        <li>第04个li</li>
        <li>第05个li</li>
    </ul>
</div>
```

#### 清除浮动4: 内墙法
```html
<style type="text/css">
    li {
        float: left;
        width: 90px;
        height: 40px;
        background-color: gold;
        text-align: center;
    }

    .cl {
        clear: both;
    }

</style>
......
<div>
    <ul>
        <li>第1个li</li>
        <li>第2个li</li>
        <li>第3个li</li>
        <li>第4个li</li>
        <li>第5个li</li>
    </ul>
    <div class="cl"></div>
</div>
<div class="div2">
    <ul >
        <li>第01个li</li>
        <li>第02个li</li>
        <li>第03个li</li>
        <li>第04个li</li>
        <li>第05个li</li>
    </ul>
</div>
```

#### 清除浮动5: `overflow:hidden;`

overflow就是“溢出”的意思， hidden就是“隐藏”的意思。  
 
```css
overflow:hidden
```

表示“溢出隐藏”。所有溢出边框的内容，都要隐藏掉。

