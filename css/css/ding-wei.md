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




