### 解析过程

`HTML`加载完毕，渲染引擎会在内存中把`HTML`文档，生成一个`DOM`树，`getElementById`是获取内中`DOM`上的元素节点。然后操作的时候修改的是该元素的属性。

### DOM
Document是文档对象模型的一部分

#### DOM的数据结构(树状)

![](/assets/DOM数据结构图.png)

#### Html的组成部分为节点(Node)
在HTML当中一切都是节点……  

1. 由结构图中我们可以看到，整个文档就是一个文档节点。
2. 每一个HMTL标签都是一个元素节点（标签）。
3. 标签中的文字则是文字节点。（文本）
4. 标签的属性是属性节点。（属性）

#### DOM节点获取

操作节点，必须首先找到该元素。

##### 通过id找到元素
返回一个元素

```js
语法：
document.getElementById("id值");
//找到id=myDiv的节点
document.getElementById("myDiv");
``` 

##### 通过标签名 
返回的是节点数组
 
```js
语法：
document.getElementsByTagName("标签名");

//找到所有的div
document.getElementsById("div");
``` 

##### 通过类名获取  
返回的是节点数组

**通过类名查找 HTML 元素在 IE 5,6,7,8 中无效**

```js
语法：
document.getElementsByClassName("类名")

//获取使用了class名为myStyle的元素
document.getElementsByClassName("myStyle");
```

### DOM访问关系
节点的访问关系，是以属性的方式存在的。  

DOM的节点并不是孤立的，因此可以通过DOM节点之间的相对关系对它们进行访问。

#### 父节点
调用者就是节点。一个节点只有一个父节点。调用方式就是节点.parentNode

```html
<div>
    <p id="myPara">这是一个段落</p>
</div>

<script>
var para = document.getElementById("myPara");
var parent = para.parentNode;
parent.style.backgroundColor = "red";
</script>
```

#### 兄弟节点
* Sibling:兄弟
* next: 下一个
* previous: 上一个

##### 下一个兄弟节点
1. nextSibling：调用者是节点。IE678中指下一个元素节点（标签）。在火狐谷歌IE9+以后都指的是下一个节点（包括空文档和换行节点）。
2. nextElementSibling：在火狐谷歌IE9都指的是下一个元素节点。

总结：**在IE678中用nextSibling，在火狐谷歌IE9+以后用nextElementSibling**

```js
下一个兄弟节点=节点.nextElementSibling || 节点.nextSibling
```

##### 上一个兄弟节点
1. previousSibling：调用者是节点。IE678中指前一个元素节点（标签）。在火狐谷歌IE9+以后都指的是前一个节点（包括空文档和换行节点）。
2. previousElementSibling：在火狐谷歌IE9都指的是前一个元素节点。

总结：**在IE678中用previousSibling，在火狐谷歌IE9+以后用previousElementSibling。**

```js
下一个兄弟节点=节点.previousElementSibling|| 节点.previousSibling
```

#### 子节点
##### 单个子节点
1. firstChild：调用者是父节点。IE678中指第一个子元素节点（标签）。在火狐谷歌IE9+以后都指的是第一个节点（包括空文档和换行节点）。
2. firstElementChild:在火狐谷歌IE9都指的第一个元素节点。

 ```js
 第一个子节点=父节点.firstElementChild || 父节点.firstChild
 ```
 
3. lastChild:调用者是父节点。IE678中指最后一个子元素节点（标签）。在火狐谷歌IE9+以后都指的是最后一个节点（包括空文档和换行节点）
4. astElementChild：在火狐谷歌IE9都指的最后一个元素节点

 ```js
 第一个子节点=父节点.lastElementChild|| 父节点.lastChild
 ```
 
##### 所有子节点
###### childNodes
是标准属性，它返回指定元素的子元素集合，包括HTML节点，所有属性，文本节点（火狐 谷歌等高本版会把换行也看做是子节点）

1. nodeType == 1  ==> 元素节点
2. nodeType == 2  ==> 属性节点
3. nodeType == 3  ==> 文本节点

```js
子节点数组 = 父节点.childNodes; //获取所有子节点
```

###### children
非标准属性，它返回指定元素的子元素集合

但它只返回HTML节点，甚至不返回文本节点，虽然不是标准的DOM属性，但它和innerHTML方法一样，得到了几乎所有浏览器的支持

children在IE6/7/8中包含注释节点，在IE678中，注释节点不要写在里面

```js
子节点数组 = 父节点.children;   用的最多.
```

### 对Dom节点的操作
节点的访问关系都是属性。节点的操作都是**函数或者方法。**

| 操作 | 解释 |
| :---: | :---: |
| 更新 | 更新该DOM节点的内容，相当于更新了该DOM节点表示的HTML的内容 |
| 遍历 | 遍历该DOM节点下的子节点，以便进行进一步操作 |
| 添加 | 在该DOM节点下新增一个子节点，相当于动态增加了一个HTML节点 |
| 删除 | 将该节点从HTML中删除，相当于删掉了该DOM节点的内容以及它包含的所有子节点 |


#### 创建节点
```js
新的标签（节点） = document.createElement(“标签名”);
```

#### 插入节点
```js
父节点.appendChild();
父节点.appendChild(新节点); //父节点的最后插入一个新节点使用方法：

父节点.insertBefore(要插入的节点，参考节点)；
父节点.insertBefore(新节点,参考节点) //在参考节点前插入;
如果参考节点为null，那么他将在节点最后插入一个节点。
```

#### 删除节点
```js
1. 用父节点删除子节点
父节点.removeChild(子节点); // 必须指定要删除的节点

2. 自己删除
自己.parentNode.removeChild(自己);
```

#### 复制节点
想要复制的节点调用函数`cloneNode()`，得到一个新节点。 方法内部可以传参，如果是true，深层复制，如果是false，只复制节点本身。

```js
新节点=要复制的节点.cloneNode(参数) ; //参数可选复制节点
```

#### 更新节点
##### 修改innerHTML
innerHTML属性，不但可以修改一个DOM节点的文本内容，还可以直接通过HTML片段修改DOM节点内部的子树

```html
<div>
    <p id="myPara">这是一个段落</p>
</div>

<script>

    var para = document.getElementById("myPara");
    var parent = para.parentNode;

    parent.innerHTML = 'DDDDDDD';
    parent.innerHTML = '<span style="color: red;"> DDDDDDD</span>';
</script>
```

###### 修改innerText或textContent

```html
<div>
    <p id="myPara">这是一个段落</p>
</div>

<script>

    var para = document.getElementById("myPara");
    var parent = para.parentNode;

    parent.textContent = 'DDDDDDD';
    parent.textContent = '<span style="color: red;"> DDDDDDD</span>';
</script>
```

#### 节点属性
注意：IE6、7不支持。调用者：节点,有参数,没有返回值。

1. 获取：getAttribute(名称)
2. 设置：setAttribute(名称, 值)
3. 删除：removeAttribute(名称)