### 概念
CSS 伪类用于向某些选择器添加特殊的效果。  

也就是说，同一个标签，根据用户的某种状态不同，有不同的样式。这就叫做“伪类”。  

类就是工程师加的，比如div属于box类，很明确，就是属于box类。  
但是a属于什么类？不明确。因为要看用户有没有点击、有没有触碰。所以，就叫做“伪类”。伪类用冒号来表示。

### 伪类

| 属性 | 含义 |
| :---: | :---: |
| :link      |  伪类将应用于未被访问过的链接。IE6不兼容，解决此问题，直接使用a标签。  |
| :hover     |  伪类将应用于有鼠标指针悬停于其上的元素。在IE6只能应用于a连接，IE7+所有元素都兼容。  |
| :active    |  伪类将应用于被激活的元素，如被点击的链接、被按下的按钮等。  |
| :visited   |  伪类将应用于已经被访问过的链接  |
| :focus     |  伪类将应用于拥有键盘输入焦点的元素。  |


### a标签的四种伪类
```css
a:link {
    color: blue;
}

a:visited {
    color: green;
}

a:hover {
    color: red;
}

a:active {
    color: yellow;
}

```

| 伪类 | 含义 |
| :---: | :---: |
| `:link` | 用户没有点击过这个链接  |
| `:visited` | 用户访问过这个链接的样式  |
| `:hover` | 鼠标悬停时链接的样式 |
| `:active` | 用户点击这个链接不松手的样式  |

**在css中四种属性必须按顺序写。**

#### 超链接的美化

a标签在使用的时候，非常的难。因为不仅仅要控制a这个盒子，也要控制它的伪类。我们一定要将a标签写在前面，:link、:visited、:hover、:active这些伪类写在后面。  

**a标签中，描述盒子； 伪类中描述文字的样式、背景。**  

```css
.nav ul li a {
    display: block;
    width: 120px;
    height: 50px;
}

.nav ul li a:link, .nav ul li a:visited {
    text-decoration: none;
    background-color: yellowgreen;
    color: white;
}

.nav ul li a:hover {
    background-color: pink;
    font-weight: 700;
    color: yellow;
}
```

##### 简写
最标准的，就是把link、visited、hover都要写。  
但是前端开发工程师在大量的实践中，发现不写link、visited浏览器也挺兼容。  
所以就把a标签简化了：a:link、a:visited都是可以省略的，简写在a标签里面。  
也就是说，a标签涵盖了link、visited的状态。  

```css
.nav ul li a {
    display: block;
    width: 120px;
    height: 50px;
    text-decoration: none;
    background-color: yellowgreen;
    color: white;
}

.nav ul li a:hover {
    background-color: pink;
    font-weight: 700;
    color: yellow;
}
```
