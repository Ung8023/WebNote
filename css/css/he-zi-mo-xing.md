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

#### padding
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

#### 去掉border

