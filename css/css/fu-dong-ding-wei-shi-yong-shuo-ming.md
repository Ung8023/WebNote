### 规避脱标流
1. 尽量使用标准流
2. 标准流解决不了的使用浮动
3. 浮动解决不了的使用定位

### 标签包含规范
1. div可以包含所有的标签。
2. p标签不能包含div h1等标签。
3. h1可以包含p，div等标签。
4. 行内元素尽量包含行内元素，行内元素不要包含块元素。

### 图片和文字垂直居中对齐
virtual-align对inline-block最敏感，默认属性是：`vertical-align:baseline;`  

| 值 | 描述  |
| :---: | :---: |
| baseline | 默认，元素放在父元素的基线上 |
| sub | 垂直对齐文本的下标 |
| super | 垂直对齐文本的上标 |
| top | 把元素的顶端与行中最高元素的顶端对齐 |
| text-top | 把元素的顶端与父元素字体的顶端对齐 |
| middle | 把此元素放置在父元素的中部 |
| bottom | 把元素的顶端与行中最低的元素的顶端对齐 |
| text-bottom | 把元素的底端与父元素字体的底端端对齐 |
| length | |
| % | 使用‘line-height’属性的百分比值来排列此元素 |
| inherit | 从父元素继承 | 

### css可见性
1. `overflow: hidden;` 溢出隐藏
2. `visibility: hidden;` 隐藏元素，隐藏之后还占据原来位置
3. `display: none;` 隐藏元素，隐藏之后不占据原来位置
4. `display: block;` 元素可见

`display: none;` 和 `display: block;` 常配合js使用
