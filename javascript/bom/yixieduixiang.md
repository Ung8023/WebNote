### Screen
window.screen 对象包含有关用户屏幕的信息。

```
screen.width：屏幕宽度，以像素为单位；
screen.height：屏幕高度，以像素为单位；
screen.colorDepth：返回颜色位数，如8、16、24。
screen.availWidth - 可用的屏幕宽度
screen.availHeight - 可用的屏幕高度
```

### Location
表示当前页面的URL信息

```js
location.hostname 返回 web 主机的域名
location.pathname 返回当前页面的路径和文件名
location.port 返回 web 主机的端口 （80 或 443）
location.protocol 返回所使用的 web 协议（http:// 或 https://）
location.href 属性返回当前页面的 URL。
location.pathname 属性返回 URL 的路径名。
location.assign() 方法加载新的文档,并记录到历史中。设置location.href  就会调用assign()。一般使用location.href 进行页面之间的跳转
location.search 查询字符串
location.hash  返回url中#后面的内容，包含#
location.replace() 替换浏览器地址栏的地址，不会记录到历史中
location.reload() 重新加载
```

### navigator对象
表示浏览器的信息,`navigator`对象的信息具有误导性，不应该被用于检测浏览器版本: 

navigator 数据可被浏览器使用者更改
浏览器无法报告晚于浏览器发布的新操作系统

```js
window.navigator 的一些属性可以获取客户端的一些信息userAgent (系统，浏览器)platform (浏览器支持的系统，win/mac/linux)
navigator.appName：浏览器名称；
navigator.appVersion：浏览器版本；
navigator.language：浏览器设置的语言；
navigator.platform：操作系统类型；
navigator.userAgent：浏览器设定的User-Agent字符串。
```

### history
保存了浏览器的历史记录，一般不使用

```js
后退
history.back()
history.go(-1)

前进
history.forward()
history.go(1)

刷新
history.go(0)
```