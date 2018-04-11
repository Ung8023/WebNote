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

```js

```

### 对Dom节点的操作

| 操作 | 解释 |
| :---: | :---: |
| 更新 | 更新该DOM节点的内容，相当于更新了该DOM节点表示的HTML的内容 |
| 遍历 | 遍历该DOM节点下的子节点，以便进行进一步操作 |
| 添加 | 在该DOM节点下新增一个子节点，相当于动态增加了一个HTML节点 |
| 删除 | 将该节点从HTML中删除，相当于删掉了该DOM节点的内容以及它包含的所有子节点 |


