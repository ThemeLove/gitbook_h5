#### 	
	1.浮动和定位会使元素脱离标准流，可以让原来不是块级元素的元素变成块级元素，可以给它们设置宽高，由于脱离了标准流，所以它们不占用空间，所以它们不参与父盒子的宽高计算，不能撑开父盒子。除非给它们的父盒子清除浮动。
####2.margin的合并： 
	2个相邻的上下盒子之间如果都设置了margin,比如上盒子设置了margin-bottom:100px,下盒子设置了margin-top:50px,最终2个盒子之间的margin值为100px;浏览器会取2者中的最大值作为最终值。
	要解决这个问题，最常用的办法就是给父盒子添加overflow:hidden属性。 
####3.属性的继承（有些属性可以继承，有些属性不能继承）
	可以继承的属性：text-align
	例如：比如text-align,比如li>a>img+p这种布局，给li设置了 
		 text-align属性,那么a标签也就继承了这种属性，其中的img和p也都会水平居中。 
	不可以继承的属性：display 
	例如：display,比如div>a>img+p这种布局，给a标签设置宽高没有用，因为a不是块级元素，即使它的父级元素是div是块级元素（display:block）,也不行；需要手动给a添加display:block,设置的宽高才有效。 

####4.使用js添加的样式为行内式样式，可以通过审查元素查看。
####5.touchstart、touchmove、touchend是移动端特有事件。
####6.webkitTransitionEnd :添加过渡结束事件，该事件是C3新添加事件，需要添加浏览器私有化前缀.
####7.white-space:nowrap :可以让内容在一行，不换行
####8.让子控件顶端对齐可以让设置父控件font-size:0,让后在给要对齐的子控件这种display:inline-block,vertical-align:top