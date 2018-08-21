##-------------------------------上午------------------------------- 
####1.常用选择器  
	之前学过的选择器 
	标签选择器						div 
	类名选择器						.box 
	id选择器							#box 
	后代选择器						div p  
	子代选择器						div>p
    交集选择器						div.box 
	并集选择器						div,p,span  
	通配符选择器						*   
	div+p  包含关系不生效，兄弟关系才生效，并且需要紧挨着，中间有其他元素间隔第一个p也不生效
    div~p  包含关系不生效，兄弟关系才生效，不需要紧挨着，后面所有的同级p都生效
	
####2.属性选择器 

	属性选择器	[]	  	通过标签属性来选择

	属性选择器：语法 
	标志性符号：[] 
	^:开头 
	$:结尾  
	*：包含 
	
	示例： 
	E[title]			:选中页面中的E元素，并且E需要带有title属性 
	E[title="abc"]		:选中页面中的E元素，并且E需要带有title属性，属性值为"abc" 
	E[title^="abc"]		:选中页面中的E元素，并且E需要带有title属性，属性值以"abc"开头 
	E[title$="abc"]		:选中页面中的E元素，并且E需要带有title属性，属性值以"abc"结尾 
	E[title*="abc"]		:选中页面中的E元素，并且E需要带有title属性，属性值中包含"abc"  
####3.伪类选择器 
	标志性符号	：	
	:hover		鼠标悬浮在上面的状态
	:link 		未访问过的状态	
	:active 	点击时的状态
	:visited	点击过后的状态 
####4.结构伪类 
	E:first-child			选中E父盒子中的第一个E 
	E:last-child			选中E父盒子中的最后一个E  
	E:nth-child(5)			选中E父元素中的第5个子元素 
	  n:0,1,2,3,4....,当n<1是无效 
	偶数：2n even 
	奇数：2n+1 odd 
	前5个：-n+5 
	E：nth-last-child(3):	在E父元素中，从后向前选择，选中倒数第三个 
	注意：所选到的元素类型，必须是指定的类型E,否则选择不到 

####empty伪类   
	empty伪类表示一种状态，表示只有元素内容为空时才显示指定的样式，空格也是内容，不显示伪类样式
####target伪类 
	target伪类要配合a标签锚点使用，表示被激活的状态 
	示例：
	<a href="#title">我是a</a>
	<h2 id="title">我是h2</h2>
 
	h2:target{
		color:red;
	}
	
	当点击a链接跳转到h2时，h2被激活，target伪类生效，使h2字体变红。 

####伪元素before和after 
	1.伪元素相当于用css模拟出html的效果，显示到网页上,
    2.模拟出的伪元素相当于是选中元素的子元素，选中元素的属性对伪元素也起作用
    3.必须要有content属性才行 

####伪元素first-letter（首字母）、first-line（首行） 
	示例：
	p::first-letter{
	   color:red;
	} 

	p::first-line{
	   color:blue
	}
####伪元素selection（选中区域）
	p::selection{
	   color:red;
	}
		
	

##-------------------------------下午------------------------------- 

####CSS2中的颜色模式
	GBA 
####CSS3中新增两种颜色模式 
	RGBA 
		R：red 
		G：green 
		B：blue 
		A：alpha 
	HSLA 
		H:色调 		取值范围：0~360	
		S:饱和度		取值范围：0%~100%
		L:亮度 		取值范围：0%~100%
		A:alpha 	取值范围：0~1

	只要能设置颜色的地方都可以用这两种模式，border也可以   
####CSS3中的文本阴影text-shadow 
		text-shadow :水平位移像素 竖直位移像素 模糊长度 颜色
        水平位移和竖直位移：负值---阴影在上，正值---阴影在下
        多个阴影效果并列书写，使用逗号隔开 

####CSS3盒子模型  
	传统盒子模型 
	1.宽高:border+padding+content 
	2.内容区域大小不变 
	3.总体大小变化  
	CSS3盒子模型 
	三个盒子：content-box padding-box border-box 

	box-sizing:border-box（内减模式）	：设置盒子模型中最大盒子大小，如果再加上border和padding,只会减小盒子内容区域 

	content-box(外加模式)（默认值） ：设置盒子内容区域的大小，如果再加上border和padding,整体盒子大小会增大

	当box-sizing:content-box 时就是传统CSS中的盒子模型 

####CSS3的现状 
	css3浏览器支持程度较差，需要添加浏览器私有化前缀  
    兼容各大浏览器写法,私有化前缀
    -webkit-       google 苹果
    -moz-          火狐
    -o-            欧朋
    -ms-           微软  

	最后加上无私有化前缀的正常写法 

	示例： 
    background: -webkit-linear-gradient(red,green,blue);     兼容google、苹果safari
    background: -moz-linear-gradient(red,green,blue);		 兼容火狐 
    background: -o-linear-gradient(red,green,blue);		     兼容欧朋 
    background: -ms-radial-gradient(red,green,blue);		 兼容微软IE
    background: linear-gradient(red,green,blue);			 无私有化前缀正常写法


            