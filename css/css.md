### 概述
CSS描述页面的样式，是casading style sheet(层叠样式表)的简写。

### CSS书写位置:

1. 当前文件书写

    ```html
    <style type="text/css">
        /* 在此处书写css代码 */
        p {
            background-color: antiquewhite;
        }
    </style>
    ```
2. 外部文件书写
    
    ```html
    <link rel="stylesheet" href="../css/a.css">
    ```
    
### CSS 语法：
**css对换行不敏感，对空格也不敏感。**但是一定要有标准的语法。**冒号，分号都不能省略。**

```html
选择器{
    key:value;
    key:value;
    ......
}
```

### 常见属性
#### 字符颜色：
`color:red;`  

color属性的值，可以使英文单词，red、blue、yellow等，也可以是rgb，十六进制。  
快捷键: c + tab
#### 字号大小
`font-size:40px;`

快捷键：fiz + tab

#### 背景颜色
`background-color:blue;`

快捷键：bgc + tab

#### 字体加粗
`font-weight:bold;`快捷键：fwb + tab  
`font-weight:normal;` 快捷键：fwn + tab

#### 斜体：
