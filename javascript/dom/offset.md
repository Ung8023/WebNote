 js中有一套方便的获取元素尺寸的办法就是offset系列属性.
 
 ### 标注图
 
 ![](/assets/DOMOffset图示.png)
 
 
 ### offsetWidth与offsetHeight
 得到对象自己的宽度和高度
 
 #### offsetWidth
 使用`object.style.width`只能获取到内嵌式写法的width
 
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
 
 ```html
 <style type="text/css">
 div {
     width: 200px;
     height: 300px;
     border-left: 3px red solid;
     background-color: pink;
     padding: 10px;
 }
</style>

<body>
    <div id="js-div1">
afsasfasfasf
    </div>
    <div style="width: 200px;" id="js-div2">

    </div>
<script>
    let elementById = document.getElementById("js-div1");
    let elementById2 = document.getElementById("js-div2");
    console.log("通过style获取的width： " + elementById.style.width); // ""
    console.log("通过style获取的div2的width： " + elementById2.style.width); //"200px"
    console.log("通过offsetWidth获取的width： " + elementById.offsetWidth); //223
</script>
</body>
 ```
 
#### offsetHeight
 
 ```js
console.log("通过style获取的height： " + elementById.style.height); // ""
console.log("通过style获取div2的height： " + elementById2.style.height); //"200px"
console.log("通过offsetHeight获取的height： " + elementById.offsetHeight); //320
 ```
 
### offsetLeft与offsetTop
返回距离上级盒子（最近的带有定位）左边或上边的位置

如果父级都没有定位则以body 为准，这里的父级指的是所有上一级 不仅仅指的是 父亲 还可以是 爷爷 曾爷爷 曾曾爷爷。

```html
<style type="text/css">
    #js-div01 {
        width: 500px;
        height: 500px;
        background-color: red;
        border: 10px solid blue;
    }

    #js-div02 {
        width: 100px;
        height: 100px;
        background-color: pink;
        border: 5px solid green;
    }
</style>


```
