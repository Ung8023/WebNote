### 盒子模型
![](/assets/盒子模型.png)

#### 盒子中的区域
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

#### width和height
css中定义的width和height不一定是盒子的真实占有宽高。

1. 真实占有宽度 = 左border + 左padding + width + 右padding + 右border
2. 真实占有高度 = 上border + 上padding + height + 下padding + 下border

##### 两个300*300的盒子：

```html

```