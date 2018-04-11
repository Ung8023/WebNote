### 获取系统当前时间
```js
var nowLocal = new Date();
nowLocal; // Wed Apr 11 2018 20:22:30 GMT+0800 (CST)
nowLocal.getFullYear(); // 2018, 年份
nowLocal.getMonth(); // 3, 月份，注意月份范围是0~11，3表示四月
nowLocal.getDate(); // 11, 表示11号
nowLocal.getDay(); // 3, 表示星期三
nowLocal.getHours(); // 20, 24小时制
nowLocal.getMinutes(); // 22, 分钟
nowLocal.getSeconds(); // 30, 秒
nowLocal.getMilliseconds(); // 875, 毫秒数
nowLocal.getTime(); // 1523431441290, 以number形式表示的时间戳

```