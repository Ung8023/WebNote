在触发DOM上的某个事件时，会产生一个事件对象`event`，这个对象中包含着所有与事件有关的信息。所有浏览器都支持`event`对象，但支持的方式不同。 

比如鼠标操作时候，会添加鼠标位置的相关信息到事件对象中

### event支持
普通浏览器支持event

ie678支持 window.event

```js
var event = event || window.event;
```

```js
document.onclick = function(event){  // 文档中点击
    var event = event || window.event;   // 兼容性写法
    console.log(event.clientY);
    console.log(event.pageY);
    console.log(event.screenY);
}
```

### event常用属性

| 属性   | 说明 |
| :---: | :---: |  
| data     | 返回拖拽对象的URL字符串（dragDrop）  |
| width    | 该窗口或框架的高度  |
| height   | 该窗口或框架的高度  |
| pageX    | 光标相对于该网页的水平位置（ie无）  |
| pageY    | 光标相对于该网页的垂直位置（ie无）  |
| screenX  | 光标相对于该屏幕的水平位置  |
| screenY  | 光标相对于该屏幕的垂直位置  |
| target   | 该事件被传送到的对象  |
| type     | 事件的类型  |
| clientX  | 光标相对于该网页的水平位置 （当前可见区域）  |
| clientY  | 光标相对于该网页的水平位置  |