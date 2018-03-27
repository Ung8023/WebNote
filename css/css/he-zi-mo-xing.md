### 盒子模型
![](/assets/盒子模型.png)

#### 盒子中的区域
主要属性:  

* width: 内容宽度。(不是盒子的宽度)
* height: 内容高度。(不是盒子的高度)
* padding: 内边距
* border: 边框
* margin: 外边距
  
  
```html
/*这个盒子的width为300，height为300，但是真实占有的宽高为:342x342，因为要加上padding、border */
div.box {
    width: 300px;
    height: 300px;
    border: solid red 1px;
    padding: 20px;
}
......
<div class="box">
这里是文字文字文字文字这里是文字文字文字文字这
里是文字文字文字文字这里是文字文字文字文字这里
是文字文字文字文字这里是文字文字文字文字这里是
文字文字文字文字这里是文字文字文字文字这里是文
字文字文字文字这里是文字文字文字文字
</div>
```

#### width和height
css中定义的width和height不一定是盒子的真实占有宽高。

1. 真实占有宽度 = 左border + 左padding + width + 右padding + 右border
2. 真实占有高度 = 上border + 上padding + height + 下padding + 下border

##### 两个300*300的盒子：

```html
<style type="text/css">
    div.box1 {
        width: 280px;
        height: 280px;
        padding: 15px;
        border: solid 5px red;
    }

    div.box2 {
        width: 280px;
        height: 280px;
        padding: 10px;
        border: solid 10px green;
    }

</style>
......
<body>
    <div class="box1">第一个盒子</div>
    <div class="box2">第二个盒子</div>
</body>
```

两个盒子的盒模型，占有宽高都是300*300：  
![](/assets/两个300x300盒子.png)

#### padding
padding就是内边距，padding区域有背景颜色(css2.1前提)，并且背景颜色一定和内容区域的相同。background-color将填充所有boder以内的区域。
  
padding是4个方向的，所以能够分别描述4个方向的padding，有两种方式:  

1. 把4个方向的值分开来写
    * `padding-top: 20px;`
    * `padding-right: 20px;`
    * `padding-bottom: 20px;`
    * `padding-left: 20px;`
2. 使用连写方式:
    
    ```html
        padding:30px 20px 40px 100px;
    ```

##### padding 属性连写：
书写顺序： `上 右 下 左`

1. 四个属性全写

    ```html
    .box {
        padding: 10px 20px 30px 40px;
    }
    ```
    
2. 只写3个值

    ```html
    .box {
        /* 最后一个应该是左，没写那么和右一样 */
        padding: 10px 20px 30px; 
    }
    ```

3. 只写两个值
    
    ```html
    .box {
        padding: 10px 20px;
    }
    ```