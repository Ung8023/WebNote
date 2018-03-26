### 继承性
有一些属性，当给自己设置的时候，自己的后代都继承上了，这个就是继承性。

#### 那些属性能继承
color、 text-开头的、line-开头的、font-开头的。  
这些关于**文字样式**的，都能够继承； 所有**关于盒子的、定位的、布局的属性**都**不能继承**。  
继承性是从自己开始，直到最小的元素。  

如果所有的页面的文字都是红色，都是16px，可以利用继承性:  

```html
body {
    color: red;
    font-size: 16px;
}
```

### 层叠性
是css处理冲突的能力

#### 权重
##### 选择上了某个元素
当选择器，**选择上了**某个元素的时候，那么要这么统计权重(权重计算没有兼容性问题)：  
**id的数量，类的数量，标签的数量**  

```html
<style type="text/css">
    /*权重为 1,1,1 */
    #hezi1 .box2 p {
        color: red;
    }
    /*权重为 1,0,3*/
    div div #hezi3 p{
        color: blue;
    }
    /*权重为 0,3,4*/
    div.box1 div.box2 div.box3 p {
        color: green;
    }
</style>
......
<div id="hezi1" class="box1">
    <div id="hezi2" class="box2">
        <div id="hezi3" class="box3">
            <p>我是什么颜色</p> // 为红色
        </div>
    </div>
</div>
```

不进位，实际上能进位（255个标签，等于1个类名）但是没有实际意义！  

**如果权重一样**，谁写在后面谁起作用。

```html
<style type="text/css">
    /* 权重为 1,1,1 */
    #hezi1 .box1 p {
        color: red;
    }
    /* 权重为 1,1,1 */
    #hezi2 div .pp {
        color: blue;
    }
</style>
......
<div id="hezi1" class="box1">
    <div id="hezi2" class="box2">
        <div id="hezi3" class="box3">
            <p class="pp">我是什么颜色</p>//为蓝色
        </div>
    </div>
</div>
```

####  通过继承影响
如果不能直接选中某个元素，通过继承性影响的话，那么权重是0。  

开始计算权重之前，一定要看是否选中了文字所在的最内层标签。如果没选中则权重为0。

```html
#hezi1 #hezi2 #hezi3 {
    color: red;
}

div.box div.box div.box {
    color: blue;
}

p {
    color: green;
}
......
<div class="box" id="hezi1">
    <div class="box" id="hezi2">
        <div class="box" id="hezi3">
            <p>我是什么颜色</p> //绿色
        </div>
    </div>
</div>
```

##### 就近原则
###### 选中的层级不同
如果权重都是0，并且没选中，那么谁描述的层级距离目标近谁起作用。

```html
#hezi1 #hezi2 {
    color: red;
}

div.box div.box div.box {
    color: blue;
}
......
<div class="box" id="hezi1">
    <div class="box" id="hezi2">
        <div class="box" id="hezi3">
            <p>我是什么颜色</p> //蓝色
        </div>
    </div>
</div>
```

###### 选中的层级相同
如果权重都是0，并且没选中，那么谁描述的层级距离目标一样，那么再按权重的规则。

```html
<style type="text/css">
    #hezi1 #hezi2 #hezi3{
        color: red;
    }

    div.box div.box div.box {
        color: blue;
    }
</style>
......
<div class="box" id="hezi1">
    <div class="box" id="hezi2">
        <div class="box" id="hezi3">
            <p>我是什么颜色</p> //红色
        </div>
    </div>
</div>
```

#### 同一个标签，携带了多个类名，有冲突    
文字为红色。当两个选择器对同一个标签的同一属性都有设置时，就会发生冲突。这个时候以css中后书写的为准，**与标签使用css的顺序无关，只与css的书写顺序有关。***  
  
```html
<style type="text/css">
    .green {
        color: green;
    }

    .red {
        color: red;
    }
</style>
......
<div>
    <p class="red green"> 我是什么颜色</p>// 红色
</div>
```

##### important
important是英语里面的“重要的”的意思。我们可以通过语法：`k:v !important;`来给一个属性**提高权重。**这个属性的权重就是**无穷大。**

```html
<style type="text/css">
    .green {
        color: green !important;
    }

    .red {
        color: red;
    }
</style>
```

###### !important提升的是一个属性，而不是一个选择器
只有color属性被提升了权重，不影响font-size属性  

```html
<style type="text/css">
    .style1 {
        color: red !important;
        font-size: 18px;
    }

    .style2 {
        color: green;
        font-size: 12px;
    }
</style>
......
<div>
    <p class="style1 style2">我什么颜色多大？</p> //红色，12px;
</div>
```

###### ！important不影响继承的权重
!important无法提升继承的权重，该是0还是0。  

```html
<style type="text/css">
    div {
        /*由于div是通过继承性来影响文字颜色的，所以!important无法提升它的权重，权重依然是0。*/
        color: red !important;
    }

    p {
        color: green;
    }
</style>
......
<div>
    <p >我什么颜色？</p> //绿色
</div>
```

###### !important不影响就近原则

```html
<style type="text/css">
    div .div4 {
        color: red !important;
    }

    div .div5 {
        color: green;
    }

</style>
......
<div>
    <div class="div2">
        <div>
            <div class="div4">
                <div class="div5">
                    <p>我是什么颜色</p> //依然是绿色，
                </div>
            </div>
        </div>
    </div>
</div>
```

##### 权重总结
 