#### 浏览器默认文字大小
16px

### 行高定义
行高： 基线与基线之间的距离  

行高 = 文字高度 + 上下边距

行高、字号，一般都是偶数。

#### 单行文本居中
**一行文字** 行高和父元素高度一致的时候，垂直居中显示

```html
div {
    height: 200px;
    background-color: orange;
    line-height: 200px;
}
......
<body>
    <div>asjfkasjfklajsfklajfskl</div>
</body>
```

#### 多行文本居中 需要设置padding
只适用于单行文本垂直居中！！不适用于多行。如果想让多行文本垂直居中，需要设置盒子的padding  

```html
<style type="text/css">
    div {
        line-height: 20px;
        background-color: yellow;
        height: 170px;
        padding-top: 130px;
    }
</style>
.......
<body>
    <div>asfahfjahfjkahsfjkahsfjkhasfjk
    asdgadsgadgadsgadsgadgadsgadsgasdgasdg
    asgadsgadsgasgasgasdgadsgadgadgadsgasdg
    asdgadsgadsgadsgadgadgasgadsgadsgadsgasdg</div>
</body>
```

### 行高单位
