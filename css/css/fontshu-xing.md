### font常用属性
| 属性 |  含义 |
| :---: | :---: |
| `font-size: 16px;`  | 文字大小 |
| `font-weight: 700;` | 值从100-900，文字粗细，不推荐使用font-weight:bold; |
| `font-family: 微软雅黑;`  |  文本的字体 |
| `font-style: normal 或 italic;` | normal 默认值  italic  斜体 |
| `line-height:` | 行高 |


```css
p {
    font-style: italic;
    font-weight: 700;
    font-size: 16px;
    line-height: 16px;
    font-family: 微软雅黑;
}
```
### 文本属性连写
```css
font: font-style font-weight font-size/line-height font-family;
```

font:后边写属性的值。一定按照书写顺序。  
文本属性连写文字大小和字体为必写项。  

```csss
div {
    font: normal 700 16px/16px 微软雅黑;
}

span {
    font: 16px/16px "Microsoft YaHei";
}
```

### font-family
#### 设置字体
常见字体英文名与unicode编码  

| 字体 | 英文名 | unicode |
| :---: | :---: | :---: |
| 宋体 | SimSun | \5B8B\4F53 |
| 新宋体       | NSimSun          | \65B0\5B8B\4F53 |
| 黑体        |  SimHei          |  \9ED1\4F53 |
| 微软雅黑     |  microsoft yahei |  \5FAE\8F6f\96C5\9ED1 |
| 楷体_GB2312 |  KaiTi_GB2312    |  \6977\4F53_GB2312 |
| 隶书        |  LiSu            |  \96B6\4E66 |
| 幼圆        |  YouYuan         |  \5E7C\5706 |
| 华文细黑     |  STXiHei         | \534E\6587\7EC6\9ED1 |
| 细明体       |  MingLiU         | \7EC6\660E\4f53 |
| 新细明体     | PMingLiU        | \65B0\7EC6\660E\4f53 |


##### 写中文名
```css
p {
    font-family: 微软雅黑;
}
```

##### 写英文名
```css
font-family: "Microsoft YaHei";
```

##### 使用unicode编码
```css
font-family: \5B8B\4F53;
```

**获取字体的unicode**  

1. 浏览器打开console
2. 输入`escape("字体")`,使用英文的括号和双引号。

#### 注意点
##### 网页中不是所有字体都能用哦，因为这个字体要看用户的电脑里面装没装。
```css
font-family: "华文彩云";
```

如果用户电脑中没有这个字体，则会变成宋体。  

**页面中，中文我们只使用： 微软雅黑、宋体、黑体。 如果页面中，需要其他的字体，那么需要切图。英语：Arial 、 Times New Roman**

##### 使用备选字体
为了防止用户电脑里面，没有微软雅黑这个字体。  
就要用英语的逗号，隔开备选字体，就是说如果用户电脑里面，没有安装微软雅黑字体，那么就是宋体。  
备选字体可以有无数个，用逗号隔开。  

```css 
font-family: "微软雅黑","宋体";
```

##### 可选字体书写顺序
我们要将英语字体，放在最前面，这样所有的中文，就不能匹配英语字体，就自动的变为后面的中文字体  

```css
font-family: "Times New Roman","微软雅黑","宋体";
```















