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
2. 做绝对定位的参考，子绝父相（讲绝对定位的时候说）

#### 定位值
可以用left、right来描述盒子右、左的移动；  
可以用top、bottom来描述盒子的下、上的移动。
