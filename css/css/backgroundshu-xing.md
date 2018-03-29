### css中颜色表示方法：
1. 英文单词
2. rgb表示法
3. 十六进制表示法

#### 用英语单词表示
能够用英语单词来表述的颜色，都是简单颜色。

```css
background-color: red;
```

#### 用rgb方法来表示
1. rgb表示三原色“红”red、“绿”green、“蓝”blue。  
2. 光学显示器，每个像素都是由三原色的发光原件组成的，靠明亮度不同调成不同的颜色的。  
3. 用逗号隔开，r、g、b的值，每个值的取值范围0~255，一共256个值。

```css
background-color: rgb(255, 0, 0);
```

#### 使用16进制表示
`#FF0000`以#开头的都是16进制。也是两位两位看，看r、g、b，但是没有逗号隔开。  
ff就是10进制的255 ，00 就是10进制的0，00就是10进制的0。所以等价于rgb(255,0,0);

##### 16进制简化写法
十六进制可以简化为3位，所有#aabbcc的形式，能够简化为#abc;

```css
background-color: #123;
background-color: #112233;
```

### background-color属性
在css中通过`background-color: 颜色; `来指定背影颜色  

```css
background-color: red;
background-color: #f00;
background-color: #FF0000;
```

### background-image属性
用于给盒子加上背景图片：  

```css
background-image: url(../css02/1.jpg);
```

url()表示网址，uniform resouces locator 统一资源定位符。

### background-repeat属性
设置**背景图**是否重复的，重复方式的。

```css
background-repeat: no-repeat | repeat | repeat-x | repeat-y | no-repeat;
```

### background-position属性
#### 含义
position就是“位置”的意思。background-position就是背景定位属性,定位属性可以为负数。  

```css
background-position: 向右偏移量 向下偏移量
```

#### css精灵
“css精灵”，英语css sprite，所以也叫做“css雪碧”技术。是一种CSS图像合并技术，该方法是将小图标和背景图像合并到一张图片上，然后利用css的背景定位来显示需要显示的图片部分。

css精灵有什么优点，就是减少了http请求。比如4张小图片，原本需要4个http请求。但是用了css精灵，小图片变为了一张图，http请求只有1个了

#### 使用单词描述
```css
background-position: 描述左右 描述上下;
```

* 描述左右的词：left center right
* 描述上下的词：top  center bottom

##### EG
1. 左下角
    
    ```css
    background-position: left bottom;
    ```

2. 右上角

    ```css
    background-position: right top;
    ```
    
### background-attachment
背景是否固定。  

```css
background-attachment: fixed;
```