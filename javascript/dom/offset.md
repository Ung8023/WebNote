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

如果父级都没有定位则以`body`为准，这里的父级指的是所有上一级 不仅仅指的是 父亲 还可以是 爷爷 曾爷爷 曾曾爷爷。

`offsetLeft`从父级的`padding`开始算，父亲的`border`不算

#### 不带定位 

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

<body>

<div id="js-div01">
    <div id="js-div02">

    </div>
</div>

<script>
let div1 = document.getElementById("js-div01");
console.log("div1 offsetLeft = " + div1.offsetLeft); // 8
console.log("div1 offsetTop = " + div1.offsetTop); //8

let div2 = document.getElementById("js-div02");
console.log("div2 offsetLeft = " + div2.offsetLeft); //18
console.log("div2 offsetTop = " + div2.offsetTop); //18
</script>
</body>
```

#### 带定位 

```html
<style type="text/css">
    #js-div01 {
        width: 500px;
        height: 500px;
        background-color: red;
        border: 10px solid blue;
        position: relative;
    }

    #js-div02 {
        width: 100px;
        height: 100px;
        background-color: pink;
        border: 5px solid green;
    }
</style>

<body>

<div id="js-div01">
    <div id="js-div02">

    </div>
</div>

<script>
let div1 = document.getElementById("js-div01");
console.log("div1 offsetLeft = " + div1.offsetLeft); // 8
console.log("div1 offsetTop = " + div1.offsetTop); //8

let div2 = document.getElementById("js-div02");
console.log("div2 offsetLeft = " + div2.offsetLeft); //0
console.log("div2 offsetTop = " + div2.offsetTop); //0
</script>
</body>
```

#### offsetTop与style.top区别
1. 最大区别在于`offsetLeft`可以返回没有定位盒子的距离左侧的位置。 而`style.top`不可以, 只有定位的盒子才有`left、top、right`
2. `offsetTop`返回的是数字，而`style.top`返回的是字符串，除了数字外还带有单位：`px`
3. `offsetTop` 只读，而 `style.top` 可读写
4. 如果没有给`HTML`元素指定过`top`样式，则`style.top`返回的是空字符串
5. **style.left 只能得到行内样式(嵌入式方式写的css)，offsetLeft 随便**

### offsetParent
返回改对象的父级（带有定位）对象


