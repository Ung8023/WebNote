### 事件三要素
1. 事件源(从哪里发起的事件)
2. 事件(什么事件)
3. 事件处理程序(出发了事件需要做的事情)

#### 事件源
事件发起者。

#### 事件
如何触发的事件，鼠标经过、按键盘.....

| 事件名       | 说明 |
| :---: | :---: |
| onclick     | 鼠标单击 |
| ondblclick  | 鼠标双击 |
| onkeyup     | 按下并释放键盘上的一个键时触发  |
| onchange    | 文本内容或下拉菜单中的选项发生改变 |
| onfocus     | 获得焦点，表示文本框等获得鼠标光标。 |
| onblur      | 失去焦点，表示文本框等失去鼠标光标。 |
| onmouseover | 鼠标悬停，即鼠标停留在图片等的上方 |
| onmouseout  | 鼠标移出，即离开图片等所在的区域 |
| onload      | 网页文档加载事件 |
| onunload    | 关闭网页时 |
| onsubmit    | 表单提交事件 |
| onreset     | 重置表单时 |

#### 事件处理程序
```js
事件源.事件 = function() {
    事件处理;
}
```

#### 示例
```html
<body>
    <div id="demo"></div>
    <button id="btn">点我一下</button>
<script type="text/javascript">
    var demo = document.getElementById("demo");
    var btn = document.getElementById("btn");
    btn.onclick = function () {
        demo.style.backgroundColor = "blue";
    }
</script>
</body>
```

