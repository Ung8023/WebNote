#### 定义滚动

滚动的内容可以是文字，图片，也可是由程序生成的文字或图片

```html
<marquee width="500px" height="500px" bgcolor="red" behavior="alternate"  direction="down" loop="-1">
    <div width="50px" height="50px" bgcolor="blue">
        我要开始滚了
    </div>
</marquee>
```

| 属性 | 值 |
| :---: | :---: |
| height | 高度 |
| width | 宽度 |
| behavior | alternate\(两端之间滚动\) scroll\(从一端滚到另一端，会重复\) slide（从一端滚到另一端，不会重复） |
| direction | down/left/right/up |
| loop | 设置滚动次数\(-1 可一直滚动\) |



