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

