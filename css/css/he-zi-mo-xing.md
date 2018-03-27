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
div.box {
    width: 300px;
    height: 300px;
    border: solid red 1px;
    padding: 20px;
    margin: 20px;
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
