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