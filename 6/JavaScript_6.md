# JavaScript 运动

### 运动基础

让 Div 运动起来

速度——物体运动的快慢

运动中的 Bug

不会停止 -->临界值问题

速度取某些值会无法停止

到达位置后再点击还会运动	-->	clearInterval()

重复点击速度加快

```javascript
window.onload = function () {
	var oBtn = document.getElementById('btn1');
	var oDiv = document.getElementById('div1');
	var timer = null;

	oBtn.onclick = function (){
		clearInterval(timer);	//保证就1个定时器
		timer = setInterval(function () {
			var speed = 1;
			if(oDiv.offsetLeft > 300){
				clearInterval(timer);
			}
			else{
				oDiv.style.left = oDiv.offsetLeft + speed + 'px';
			}
			
		}, 30);

		
	}
```



运动框架

在开始运动时，关闭已有定时器

把运动和停止隔开(if / else)

运动框架实例

例子1：“分享到”侧边栏	-->	[demo2.html](./demo2.html)

通过目标点，计算速度值

例子2：淡入淡出的图片

用变量存储透明度		-->	[demo3.html](./demo3.html)

主要是设置 opcity 并为其赋值

### 缓冲运动

逐渐变慢，最后停止

距离越远速度越大

速度由距离决定

速度=(目标值-当前值)/缩放系数

例子：缓冲菜单	-->	[demo4](./demo4.html)

Bug：速度取整	speed > 0 ? Math.ceil(speed) ：Math.floor(speed)

跟随页面滚动的缓冲侧边栏

潜在问题：目标值不是整数时	parseInt();

### 运动终止条件

匀速运动：距离足够近

缓冲运动：两点重合

### 多个物体同时运动

例子：多个 Div，鼠标移入变宽	-->	[demo5](demo5.html)

单定时器，存在问题

每个 Div 一个定时器

多物体运动框架

定时器作为物体的属性

参数的传递：物体、目标值

例子：多个 Div 淡入淡出	--> [demo6](./demo.html)

所有东西都不能公用

属性与运动对象绑定：速度、其他属性值（如透明度等）

### 任意值运动框架

offset 属性的 Bug

有边框的 Div 变宽

用currentStyle / computedStyle(obj, flase)[name] 代替 offset

原有运动框架的问题

只能让某个值运动起来

如果想让其他值运动起来，要修改程序

扩展的运动框架	--> [demo7](./demo7.html)

运动属性作为参数

封装 opacity

小数的问题	--> Math.round()	主要是为了适配 IE7