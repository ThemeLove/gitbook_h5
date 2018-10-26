##移动web知识点
####1.目前移动端浏览器内核都是webkit的，所以移动web开发的兼容性会好于pc端。  
####2.viewport
 	概念：移动设备上，用来显示网页的区域。 
	如果把移动设备的浏览器（也有可能是app中的webview）,当做相框的话， 
	那么viewport就相当于相框中的画，可能会比相框大，可能比相框小，如果一样大，则皆大欢喜。 
####3.移动web的常见设置 
	<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">

	可选值：	
	width:设置layout viewport 的宽度，为一个正整数，或字符串"width-device"

	height:设置layout viewport 的高度，这个属性对我们并不重要，很少使用

	initial-scale:设置页面的初始缩放值，为一个数字，可以带小数

	minimum-scale:允许用户的最小缩放值，为一个数字，可以带小数

	maximum-scale:允许用户的最大缩放值，为一个数字，可以带小数

	user-scalable:是否允许用户进行缩放，值为"no"或"yes", no 代表不允许，yes代表允许 

####4.移动web的常用细节样式 
	清除点击高亮效果：（在移动端浏览器会遇见点击出现高亮的效果，在某项项目是不需要这个默认的效果的。那么我们通常会把这个点击的颜色设置成透明。）
	-webkit-tap-highlight-color:transparent;

	盒子模型：(通过css3的新属性box-sizing我们能够让盒子有限顾及自己的尺寸而不是内容,避免出现多余的滚动条)
 	/*设置宽度以边框开始计算*/
	-webkit-box-sizing: border-box;/*webkit内核兼容性写法*/
	box-sizing: border-box;

 	Input默认样式清除:(在移动设备的浏览器中input标签一般会有默认的样式,通过border=none,outline=none无法去除,比如立体效果,3d效果等等,我们需要添加下列样式) 
	/*在移动端清除浏览器默认样式*/
	-webkit-appearance: none; 

	最小宽度和最大的宽度:(考虑到移动设备在大尺寸的的屏幕不会过度缩放 失去清晰度,在小尺寸的屏幕中不会出现布局错乱的问题) 
	注 下列代码取值不是固定的,根据实际情况需要进行调整
	max-width: 640px;  /*在行业当中的移动端的设计图一般使用的是640px*/
	min-width: 300px;  /*在移动设备当中现在最小的尺寸320px*/ 

	结构伪类选择器:(nth-child()如果有多个不同兄弟节点获取的时候,索引需要特殊计算,我们可以限定在某一个类型上,语法如下)
	
	E:first-of-type匹配同类型中的第一个元素E。
	E:last-of-type匹配同类型中的最后一个元素E。
	E:nth-of-type(n) 匹配同类型中的第n个元素E。