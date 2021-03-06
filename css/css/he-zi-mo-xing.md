### 盒子模型
![](/assets/盒子模型.png)

### 盒子中的区域
主要属性:  

* width: 内容宽度。(不是盒子的宽度)
* height: 内容高度。(不是盒子的高度)
* padding: 内边距
* border: 边框
* margin: 外边距
  
  
```html
/*这个盒子的width为300，height为300，但是真实占有的宽高为:342x342，因为要加上padding、border */
div.box {
    width: 300px;
    height: 300px;
    border: solid red 1px;
    padding: 20px;
}
......
<div class="box">
这里是文字文字文字文字这里是文字文字文字文字这
里是文字文字文字文字这里是文字文字文字文字这里
是文字文字文字文字这里是文字文字文字文字这里是
文字文字文字文字这里是文字文字文字文字这里是文
字文字文字文字这里是文字文字文字文字
</div>
```

### width和height
css中定义的width和height不一定是盒子的真实占有宽高。

1. 真实占有宽度 = 左border + 左padding + width + 右padding + 右border
2. 真实占有高度 = 上border + 上padding + height + 下padding + 下border

#### 两个300*300的盒子：

```html
<style type="text/css">
    div.box1 {
        width: 280px;
        height: 280px;
        padding: 15px;
        border: solid 5px red;
    }

    div.box2 {
        width: 280px;
        height: 280px;
        padding: 10px;
        border: solid 10px green;
    }

</style>
......
<body>
    <div class="box1">第一个盒子</div>
    <div class="box2">第二个盒子</div>
</body>
```

两个盒子的盒模型，占有宽高都是300*300：  
![](/assets/两个300x300盒子.png)

### padding
padding就是内边距，padding区域有背景颜色(css2.1前提)，并且背景颜色一定和内容区域的相同。background-color将填充所有boder以内的区域。
  
padding是4个方向的，所以能够分别描述4个方向的padding，有两种方式:  

1. 把4个方向的值分开来写
    * `padding-top: 20px;`
    * `padding-right: 20px;`
    * `padding-bottom: 20px;`
    * `padding-left: 20px;`
2. 使用连写方式:
    
    ```css
        padding:30px 20px 40px 100px;
    ```

#### padding 属性连写：
书写顺序： `上 右 下 左`

1. 四个属性全写

    ```css
    .box {
        padding: 10px 20px 30px 40px;
    }
    ```
    
2. 只写3个值

    ```css
    .box {
        /* 最后一个应该是左，没写那么和右一样为20px; */
        padding: 10px 20px 30px; 
    }
    ```

3. 只写两个值
    
    ```css
    .box {
        /* 后面两个分别为下和左，没写则分别与上和右一样，下为10px，左为20px */
        padding: 10px 20px;
    }
    ```
    
4. 只写一个值

    ```css
    .box {
        /* 如果只写一个值，则四个方向的padding都为这个值为10px */
        padding: 10px;
    }
    ```
    
##### 利用层叠性，使用小属性覆盖大属性
类似需求，上、左、右的padding为10，下padding为15px;  

```css
.box {
    padding: 10px;
    padding-bottom: 15px;
}
```

##### 清除默认padding
一些元素，默认带有padding，比如ul标签。所以，我们为了做站的时候，便于控制，总是喜欢清除这个默认的padding：  

```css
*{
    margin: 0;
    padding: 0;
}
```

由于`*`的效率不高，所以我们使用并集选择器，罗列所有的标签

```css
body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,legend,input,textarea,p,blockquote,th,td {
        margin:0;
        padding:0
    }
```

### border
border就是边框。边框有三个要素：粗细、线型、颜色。颜色如果不写，默认是黑色。另外两个属性不写，显示不出来边框。  

#### 线型
![](/assets/border线型.png)  

##### 所有线型  

| 类型 | 描述 |
| :---: | :---: |
| none	| 定义无边框。 |
| hidden	| 与 "none" 相同。不过应用于表时除外，对于表，hidden 用于解决边框冲突。 |
| dotted	| 定义点状边框。在大多数浏览器中呈现为实线。 |
| dashed	| 定义虚线。在大多数浏览器中呈现为实线。 |
| solid	| 定义实线。 |
| double	| 定义双线。双线的宽度等于 border-width 的值。 |
| groove	| 定义 3D 凹槽边框。其效果取决于 border-color 的值。 |
| ridge	| 定义 3D 垄状边框。其效果取决于 border-color 的值。 |
| inset	| 定义 3D inset 边框。其效果取决于 border-color 的值。 |
| outset	| 定义 3D outset 边框。其效果取决于 border-color 的值。 |
| inherit	| 规定应该从父元素继承边框样式。 |

**因为不同的线型在不同的浏览器中略有差异，所以一般常用的有：solid、dashed、dotted；如果要求对页面还原度极高，那么不能使用css来制作边框。就要用到图片，就要切图了 **

#### 拆分
border是一个综合属性，  

```css
/* 把4个边框，都设置为1px宽度、线型实线、red颜色。 */
border:1px solid red;
```

border属性能够被拆分:  
1）按3要素:`border-width、border-style、border-color`   
2) 按方向：border-top、border-right、border-bottom、border-left

##### 按3要素拆开
```css
border-width:10px;    → 边框宽度
border-style:solid;     → 线型
border-color:red;      → 颜色。
```

等价于：  

```css
border:10px solid red;
```

如果某一个小要素后面是空格隔开的，那么就是**上右下左**的顺序：  

```css
border-style: solid dotted dashed;
border-color: red green blue;
border-width: 20px 10px ;
```  

![](/assets/border3要素拆分效果图.png)

##### 按方向拆分
```css
border-top: 10px solid red;
border-right: 10px solid red;
border-bottom: 10px solid red;
border-left: 10px solid red;

...等价于...
border:10px solid red;
```

**按方向还能再拆一层，就是把每个方向的，每个要素拆开，一共12条语句**  

```css
border-top-style: solid;
border-top-width: 10px;
border-top-color: red;
border-right-style: dashed;
border-right-width: 5px;
border-right-color: green;
border-bottom-style: dotted;
border-bottom-width: 1px;
border-bottom-color: orange;
border-left-style: solid;
border-left-width: 3px;
border-left-color: blue;
```

#### 边框合并(border-collapse)
```css
table {
    width: 300px;
    height: 500px;
    border: 1px solid red;
    border-collapse: collapse;
}
td {
    border: 1px solid red;
}
```

#### 获取焦点
```html
<style type="text/css">
    .username {
        border: 0 none;  /*去掉边框*/
        outline-style: none;   /*去掉轮廓线*/
        background-color: #ccc;
        border: 1px dashed green;
    }

    .username:focus {
        background: red;
    }
</style>
........
<label for="username">用户名</label><input type="text" id="username" class="username">
```

#### 去掉border
1. 去掉所有border  

    ```css
    border: none;
    ```
    
2. 去掉某一方向的border
    
    ```css
    border-left: none;
    ```

3. 通过指定border宽度为0去掉border
    
    ```css
    border-width: 0;
    border-left-width: 0;
    ```
    
### margin
使用方法与padding完全一致

#### margin塌陷现象
在标准文档流中，竖直方向的margin不叠加。  
如果不在标准流，比如盒子都浮动了，那么两个盒子之间是没有塌陷现象

#### 盒子居中`margin: 0 auto`
margin的值可以为auto，表示自动。当left、right两个方向，都是auto的时候，盒子居中了：  

```css
margin-left: auto;
margin-right: auto;

简写为
margin: 0 auto;
```

##### 注意点：
1. 使用`margin:0 auto;` 的盒子，必须有width，有明确的width
2. 只有标准流的盒子，才能使用margin:0 auto; 居中。也就是说，当一个盒子浮动了、绝对定位了、固定定位了，都不能使用`margin:0 auto;`
3. `margin:0 auto;`是在居中盒子，不是居中文本。文本的居中，要使用`text-align:center;`

#### 居中
```css
margin:0 auto;   → 让这个div自己在大容器中居中。
text-align: center;  → 让这个div内部的文本居中。
text-align:left;     文本居左
text-align:right;    文本居右
```

#### 善于使用父级的padding而不是子级的margin
如果父亲没有border，儿子的margin实际上相对于流设置的，是这一行。所以，父亲整体也掉下来了  
**margin这个属性，本质上描述的是兄弟和兄弟之间的距离； 最好不要用这个marign表达父子之间的距离。**

#### margin的IE6兼容问题

##### IE6双倍margin bug
当出现连续浮动的元素，携带和浮动方向相同的margin时，队首的元素，会双倍marign。

```html
<ul>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

**解决方案：**  

1. 使浮动的方向和margin的方向相反

    ```css
    float: left;
    margin-right: 40px;
    ```

2. 使用hack(单独给队首的元素，写一个一半的margin)

    ```html
    ul li.no1{	
        _margin-left:20px;
    }
    
    <li class="no1"></li>
    ```
    
##### 3px-bug
儿子元素右浮动用`margin-right`设置距离，导致多出3px；

```html
<style type="text/css">
*{
    margin: 0;
    padding: 0;
}
div{
    width: 400px;
    height: 400px;
    background-color: orange;
}
div p{
    margin-right: 10px;
    float: right;
    width: 100px;
    height: 100px;
    background-color: green;
}
</style>
......
<body>
<div>
    <p></p>
</div>
```
