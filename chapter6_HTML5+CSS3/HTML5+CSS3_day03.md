##-------------------------------上午------------------------------- 
####1.圆角边框 border-radius 
	border-radius
	a.既可以写固定px数值，也可以写百分比
    b."/":斜号分隔：x1 x2 x3 x4/y1 y2 y3 y4 -----> 
	  斜号之前表示上左、上右、下右、下左 （顺时针）x轴半径值，如果只有一个值，则表示4个角的值都一样，没有值的话取对角的值。 
	  斜号之后表示上左、上右、下右、下左（顺时针）y轴的半径值，如果只有一个值，则表示4个角的值都一样，如果不足4个值，则取对角的值。
    c." "空格分隔：数值1 数值2 数值3 数值4-----> 
	  表示上左、上右、下右、下左（顺时针）x和y轴半径的值，如果只有一个值，则4个角的值都一样，如果不足4个值，则取对角的值 
	d.个边角值也可以单独设置 
	border-radius-top-left-radius 
	border-radius-top-right-radius 
	border-radius-bottom-left-radius 
	border-radius-bottom-right-radius 

####2.边框阴影 box-shadow
      边框阴影
      box-shadow:水平位移 竖直位移 模糊程度 阴影大小 阴影颜色 内外阴影模式（inset） 
####3.边框图片 
      border-image-source 边框图片的资源
      border-image-slice:边框图片切片 值1 值2 值3 值4
      border-image-width:边框图片宽度
      border-image-repeat：边框图片重复策略
          repeat:正常拉伸，可能会显示不完整
          round:平铺，但是保证图片完整
          stretch:拉伸显示 
####4.背景尺寸 background 
	1.取值：数值 百分比  
	2.cover(覆盖):会保证完全覆盖盒子，但不能保证完整显示  
	3.contain（包含）:保证背景图片最大化的在盒子中等比例显示，但不保证显示完整  