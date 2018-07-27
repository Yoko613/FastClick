# FastClick移动点击

-  移动设备上的浏览器默认会在用户点击屏幕大约延迟300毫秒后才会触发点击事件，这是为了检查用户是否在做双击。为了能够立即响应用户的点击事件，才有了FastClick。



``` 不需要使用fastclick的情况 ```

```html
1、FastClick是不会对PC浏览器添加监听事件
2、Android版Chrome 32+浏览器，如果设置viewport meta的值为width=device-width，这种情况下浏览器会马上出发点击事件，不会延迟300毫秒。

<meta name="viewport" content="width=device-width, initial-scale=1">
3、所有版本的Android Chrome浏览器，如果设置viewport meta的值有user-scalable=no，浏览器也是会马上出发点击事件。
4、IE11+浏览器设置了css的属性touch-action: manipulation，它会在某些标签（a，button等）禁止双击事件，IE10的为-ms-touch-action: manipulation
```
 
 ``` 初始化fastclick方法 ```
 
 - Javascript版
 
 ``` html
 if ('addEventListener' in document) {
	document.addEventListener('DOMContentLoaded', function() {
		FastClick.attach(document.body);
	}, false);
}
 ```

- jQuery版

``` html
$(function() {
FastClick.attach(document.body);
});
```
