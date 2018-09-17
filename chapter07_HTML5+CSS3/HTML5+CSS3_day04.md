##-------------------------------上午-------------------------------  
####1.transform:rotate(range) 旋转
      transform 转换, 通常与perspective（透视）配合使用
      transform:rotateX(range) 绕X轴旋转
      transform:rotateY(range) 绕Y轴旋转
      transform:rotateZ(range) 绕Z轴旋转
      transform:rotate(range)  2d旋转角度
      transform:rotate3d()     3d旋转 
	  所有的3d旋转，对着正方向去看，都是顺时针旋转
####2.transform:translate    平移 
      transform 转换, 通常与perspective（透视）配合使用
      transform:translateX(range) 沿X轴平移
      transform:translateY(range) 沿Y轴平移
      transform:translateZ(range) 沿Z轴平移
      transform:translate()       2d平移
      transform:translate3d()     3d平移 
####3.transform:skew         倾斜 
      transform:skew(水平方向的倾斜角度，竖直方向的倾斜角度)
      transform:skewX(水平方向的倾斜角度，竖直方向的倾斜角度为零)
      transform:skewY(竖直方向的倾斜角度，水平方向的倾斜角度为零)
      transform-origin:变换的起点位置
      例如：transform-origin:left top 表示盒子的左上点不动，然后开始倾斜，默认为center center 
####4.perspective:透视 :近大远小效果，设置的用户眼镜和屏幕的距离
	 仅仅只是视觉上的呈现，并不是真正的3d 
	 透视一定要加给变幻元素的父盒子  
####5.transform-style  
	preserve-3d：指定子元素定位在三维空间内，可以让里面的子盒子保持3d效果，加给父盒子 
	float:指定子元素位于此元素所在平面内，子盒子被扁平化，默认值
##-------------------------------下午------------------------------- 

####6.css3中的动画（先定义，再调用）
	定义动画：
	一组动画定义：
	@keyframes 动画名{
		from{
		}

		to{
		}	
	}

	多组动画定义：
	@keyframes 动画名{
		0%{变幻属性}
		25%{变幻属性}
		...
		...
		100%{变幻属性}
	} 
	调用： 
	animation:动画名称 持续时间 执行次数（infinite：无限） 是否反向（alternate）  运动曲线(linear） 延迟执行时间  
	注意：动画名称 持续时间 必须要有，其他参数可选  
####7.动画属性详解 
    animation-name:动画名称
    animation-duration:单次执行时间
    animation-timing-function:动画运动时间曲线
        1.linear:匀速
        2.ease:减速
        3.ease-in:加速
        4.ease-out:减速
        5.ease-in-out:先加速后减速
        6.steps(步数)：动画分几步执行完成，可以做秒针的效果
    animation-iteration-count:重复次数 infinite 无数次
    animation-direction:执行方向
        1.normal :正常 默认值
        2.alternate:反向
    animation-delay:延迟时间
    animation-fill-mode:动画结束后盒子的状态
        1.backwards:保持动画开始前的状态
        2.forwards:保持动画结束的状态   
	animation-play-state:动画运动状态
		paused:暂停 
		running:播放

    注意：其中animation-name 和animation-duration必须要有，其他属性可以没有，为默认值 
		 多组动画以逗号分隔

	也可以连写如下：
    		动画名称  单次执行时间     运动曲线    执行次数    执行方向    保持动画结束后的状态  延迟1秒执行                
    animation:move      2s          linear       3       alternate       forwards        	1s; 
####8.多列布局 
    column-count:将文档分成多列
    column-gap:设置分栏间距
    olumn-rule:设置分栏分割线
    column-width:设置分栏的宽度，会根据列数和宽度自适应
    column-span:设置跨列,常用于标题

    注意：浏览器的兼容写法要加上各个浏览器的私有化前缀 -webkit-  -moz-  -ms- -o-

