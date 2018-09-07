##-------------------------------上午-------------------------------  
####1.伸缩布局  display:flex         
	
####2.主轴方向  flex-direction
      row:水平方向，从左到右 （默认）
      row-reverse:水平方向，从右到左
      column:竖直方向，从上到下
      column-reverse:竖直方向，从下到上 
####3.主轴对齐方式 justify-content
      justify-content:flex-start (左对齐或上对齐,默认)
      justify-content:flex-end(右对齐或下对齐)
      justify-content:center(居中)
      justify-content:space-around(平分)
      justify-content:space-between(两端对齐，中间平分) 
####4.侧轴对齐方式 align-items
      align-items:flex-start(从侧轴开始方向对齐)
      align-items:center（在侧轴方向上居中）
      align-items:flex-end（从侧轴结束方向上对齐）
      align-items:baseline（基线对齐，效果同flex-start）
      align-items:stretch(拉伸，和父盒子高度一致) 
####5.伸缩比例 flex
      flex：number 代表各个子控件占用比例
      flex: 具体宽高px值或者不写，占用本身大小，不参与比例平分