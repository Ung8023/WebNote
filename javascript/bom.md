### BOM
浏览器对象模型。使js可以与浏览器交互

### window对象

1. 所有浏览器都支持 window 对象。它表示浏览器窗口。
2. 所有 JavaScript 全局对象、函数以及变量均自动成为 window 对象的成员。
3. 全局变量是 window 对象的属性。
4. 全局函数是 window 对象的方法。
5. 甚至 HTML DOM 的 document 也是 window 对象的属性之一
6. 对象下的属性和方法调用的时候可以省略window

```js
window.document.getElementById("js-body");

等价于

document.getElementById("js-body");
```

### Window尺寸
三种方法能够确定浏览器窗口的尺寸（浏览器的视口，不包括工具栏和滚动条）

```js
对于Internet Explorer、Chrome、Firefox、Opera 以及 Safari：
window.innerHeight - 浏览器窗口的内部高度
window.innerWidth - 浏览器窗口的内部宽度

对于 Internet Explorer 8、7、6、5：
document.documentElement.clientHeight
document.documentElement.clientWidth
或者
document.body.clientHeight
document.body.clientWidth

实用的JavaScript方案
var w=window.innerWidth
|| document.documentElement.clientWidth
|| document.body.clientWidth;

var h=window.innerHeight
|| document.documentElement.clientHeight
|| document.body.clientHeight;

```

### window的一些方法

1. window.open(url,target,param)
    
    ```
    url 要打开的地址
    target新窗口的位置 _blank  _self  _parent(父框架)
    param 新窗口的一些设置
    返回值，新窗口的句柄
    ```

2. window.close() 关闭窗口
3. 新窗口.moveTo(5,5)
4. 新窗口.moveBy()
5. 新窗口.resizeTo()
6. window.resizeBy()

