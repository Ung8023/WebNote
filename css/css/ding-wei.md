### 定位分类:
1. 静态定位
2. 相对定位
3. 绝对定位
4. 固定定位

### 静态定位

### 相对定位
相对定位，就是微调元素位置的。**让元素相对自己原来的位置，进行位置调整。**  

```html
div {
    width: 200px;
    height: 200px;
}

.box1 {
    background-color: orange;
}

.box2 {
    background-color: yellowgreen;
    position: relative;
    left: 100px;
    top: 100px;
}

.box3 {
    background-color: rebeccapurple;
}
.......
<div class="box1"></div>
<div class="box2"></div>
<div class="box3"></div>
```

#### 特点
相对定位不脱离标准流，真实位置还是原来的位置，只不过影子出去了，可以到处飘

#### 用途
相对定位有坑，所以一般不用于做“压盖”效果。页面中，效果极小。就两个作用：  

1. 微调元素
2. 做绝对定位的参考，子绝父相

#### 定位值
可以用left、right来描述盒子右、左的移动；  
可以用top、bottom来描述盒子的下、上的移动。

##### 往右下移动
```css
position: relative;
top: 40px;
left: 40px;
....... 
等价于
.......
position: relative;
top: 40px;
right: -40px;
```

##### 往左上移动
```css
position: relative;
right: 40px;
bottom: -40px;
....... 
等价于
.......
position: relative;
left: -40px;
bottom: -40px;
```

### 绝对定位
绝对定位比相对定位更灵活。  

```css
.box2 {
    background-color: yellowgreen;
    position: absolute;
    left: 100px;
    top: 100px;
}
```

#### 绝对定位脱离标准流
1. 绝对定位的盒子，是脱离标准文档流的。所有的标准文档流的性质，绝对定位之后都不遵守了。  
2. 绝对定位之后，标签就不区分所谓的行内元素、块级元素了，不需要display:block;就可以设置宽、高了

```css
span {
    position: absolute;
    width: 100px;
    height: 100px;
    background-color: red;
}
```

#### 绝对定位的参考点变化
##### top
绝对定位的参考点，如果用top描述，那么定位参考点就是页面的左上角，而不是浏览器的左上角

![](/assets/绝对定位top参考位置.png)


##### bottom
如果用bottom描述，那么就是浏览器首屏窗口尺寸，对应的页面的左下角  

![](/assets/绝对定位bottom参考位置.png)


#### 绝对定位以盒子为参考点
一个绝对定位的元素，如果父辈元素中出现了也定位了的元素，那么将以父辈这个元素，为参考点。

```html
<style type="text/css">
.parent {
    border: 2px solid orange;
    width: 500px;
    height: 500px;
    position: relative;
    left: 300px;
    top: 300px;
}

.son {
    background-color: yellow;
    width: 150px;
    height: 150px;
    position: absolute;
    left: 100px;
    top: 100px;
}
</style>
......
<div class="parent">
    <div class="son"></div>
</div>
```

##### 参考对象时最近的已经定位的祖先元素，不一定是父元素
```html
<div class="box1">   →  相对定位
    <div class="box2">  →  没有定位
        <p></p>   → 绝对定位，将以box1为参考，因为box2没有定位，box1就是最近的父辈元素
    </div>
</div>
..............
<div class="box1">   →  相对定位
    <div class="box2">  → 相对定位
        <p></p>   → 绝对定位，将以box2为参考，因为box2是自己最近的父辈元素
    </div>
</div>
```

##### 任何定位都可以作为参考点
子绝父绝、子绝父相、子绝父固，都是可以给儿子定位的。  
但是，工程上子绝、父绝，没有一个盒子在标准流里面了，所以页面就不稳固，没有任何实战用途。  
工程上，“子绝父相”有意义，父亲没有脱标，儿子脱标在父亲的范围里面移动。

```html
<div>  → 绝对定位
    <p></p>  → 绝对定位，将以div作为参考点。因为父亲定位了。
</div>
```

##### 绝对定位的儿子，无视参考的那个盒子的padding
绿色部分是div的padding，蓝色部分是div的内容区域。那么此时，div相对定位，p绝对定位。p将无视父亲的padding，在border内侧为参考点，进行定位  

![](/assets/绝对定位的儿子，无视参考的那个盒子的padding.png)

##### 绝对定位的盒子居中
绝对定位之后，所有标准流的规则，都不适用了。所以margin:0 auto;失效。  
**left:50%; margin-left:负的宽度的一半。**

```css
div {
    width: 1000px;
    height: 100px;
    position: absolute;
    left: 50%;
    top: 0;
    background-color: blue;
    margin-left: -500px;
}
```

### 固定定位(IE6不兼容)
固定定位，就是相对浏览器窗口定位。页面如何滚动，这个盒子显示的位置不变。固定定位脱标！

```css
div {
    width: 1000px;
    height: 60px;
    position: fixed;
    left: 50%;
    margin-left: -500px;
    background-color: #2FBC71;
}
```
