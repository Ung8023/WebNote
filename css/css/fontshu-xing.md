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