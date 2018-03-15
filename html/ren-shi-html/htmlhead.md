### Head标签是什么
是`head`标签的内容，不会再浏览器中显示，它的作用是包含一些页面的的`元数据`

```html
<head>
  <meta charset="utf-8">
  <title>Title</title>
</head>
```
#### 添加一个标题

```html
<head>
  <meta charset="utf-8">
  <title>在此处添加Title</title>
</head>
```

### 元数据 `<meta>`元素
#### 指定文档中的字符编码
```html
<meta charset="UTF-8">
```
#### 添加网站关键字
```html
<!-- 添加关键字 -->
<meta name="keywords" content="学习html,学习Android,学习JavaScript,学习Css">
```
#### 添加作者和网页描述
```html
<!-- 添加作者 -->
<meta name="author" content="Ung8023">
<!-- 添加描述 -->
<meta name="description" content="this is description">
```
#### 网页重定向
```html
<!-- 网页重定向 -->
<meta http-equiv="refresh" content="3, http://www.baidu.com">
```
### 增加自定义图标
```html
<!-- 添加icon图标 -->
<link rel="icon" href="images/favicon.ico">
``` 
### 链接外部样式表
```html
<!-- 链接外部样式表 -->
<link rel="stylesheet" href="css/1.css">
```