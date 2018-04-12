### BOM
浏览器对象模型。使js可以与浏览器交互

### Window

#### window对象

1. 所有浏览器都支持 window 对象。它表示浏览器窗口。
2. 所有 JavaScript 全局对象、函数以及变量均自动成为 window 对象的成员。
3. 全局变量是 window 对象的属性。
4. 全局函数是 window 对象的方法。
5. 甚至 HTML DOM 的 document 也是 window 对象的属性之一

```js
window.document.getElementById("js-body");

等价于

document.getElementById("js-body");
```

#### Window尺寸
