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