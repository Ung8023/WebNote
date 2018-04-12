 js中有一套方便的获取元素尺寸的办法就是offset系列属性.
 
 ### 标注图
 
 ![](/assets/DOMOffset图示.png)
 
 
 ### offsetWidth与offsetHeight
 得到对象自己的宽度和高度
 
 #### offsetWidth
 ```js
 offsetWidth = width + border + padding
 ```
 
 ```css
 div {
  width: 220px;
  border-left: 2px solid red;
  padding: 10px;
 }
 
 div.offsetWidth = 220 + 2 + 20
 ```