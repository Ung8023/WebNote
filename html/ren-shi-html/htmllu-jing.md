### 路径

#### 相对路径

相对于文件自身出发，就是相对路径

![](/assets/路径.png)

1. 使用当前目录下的kobe.png

   ```html
    <img src="kobe.png" alt="">
   ```

2. 使用assets目录下的kobe.png

   ```html
    <img src="assets/kobe.png" alt="">
   ```

3. 使用html目录下的kobe.png

   ```html
    <img src="../kobe.png" alt="">
   ```

#### 绝对路径

从电脑的根目录开始写，一直到文件的位置

```html
<img src="C:\imges\kobe.png" alt="" />
```