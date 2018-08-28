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
	4.background-size:100% 100%;这种写法背景图片会随着浏览器窗口大小缩放而变形。
      background-size:cover:全屏背景自适应，效果更好 
	5.注意：浏览器body默认高度是0 
####5.背景图片的原点 background-origin
     background-origin:border-box; 背景图片以盒子模型border-box为原点开始平铺
     background-origin:padding-box;背景图片以盒子模型padding-box为原点开始平铺，默认值
     background-origin:content-box;背景图片以盒子模型content-box为原点开始平铺 
####6.背景裁剪 background-clip 通常要配合background-origin 使用 
	只保留（显示）background-clip对应盒子模型的背景，其他部分不显示 
####7.多背景 background   
      写法同text-shadow、box-shadow一样多个效果并列书写，使用逗号隔开，可以单独指定位置一张背景图片的位置，如果设置背景颜色，一定要写在最后
      例如：background: url("../images/bg1.png") no-repeat left top
                        ,url("../images/bg2.png") no-repeat right top
                        ,url("../images/bg3.png") no-repeat right bottom
                        ,url("../images/bg4.png") no-repeat left bottom
                        ,url("../images/bg5.png") no-repeat center #FFFFE0;/*背景颜色一定要写在最后*/ 

##-------------------------------下午------------------------------- 
####8.线性渐变 （linear-gradient）  
      方向：to left ,to right ,to top ,to bottom
      起始颜色 颜色渐变位置
      终止颜色 颜色渐变位置
####9.径向渐变 （radial-gradient）
     radial-gradient(辐射半径 at 中心的位置，起始颜色 颜色渐变位置，终止颜色 颜色渐变位置)
     辐射半径：x半径，y半径
     中心点位置：at left right center bottom top   或者具体x y点坐标
     起始颜色   颜色渐变位置
     终止颜色   颜色渐变位置
