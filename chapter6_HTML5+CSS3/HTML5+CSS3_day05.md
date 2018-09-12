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

##-------------------------------下午-------------------------------   
####6.web字体
	优点：支持程度好；.eot字体是IE专用字体 
	使用web字体步骤： 
	第一步：使用font-face声明字体：
		   @font-face{
				font-family:"字体名称"；
				src:url();
		   }  
		   例如：
		   @font-face {
				font-family: 'webfont';
    			src: url('webfont.eot'); /* IE9*/
    			src: url('webfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
    			url('webfont.woff') format('woff'), /* chrome、firefox */
    			url('webfont.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
    			url('webfont.svg#webfont') format('svg'); /* iOS 4.1- */
			}
	第二步：定义使用webfont的样式：
		   例如：
		   .web-font{
    			font-family:"webfont" !important;
    			font-size:16px;font-style:normal;
   		 		-webkit-font-smoothing: antialiased;
    			-webkit-text-stroke-width: 0.2px;
    			-moz-osx-font-smoothing: grayscale;
			}
	第三步：为文字加上对应的样式：
		   例如：
			<i class="web-font">知识就像内-裤，看不见但很重要。</i>  

####7.icon字体 
	有点：放大不失真，改变颜色，将图片当做字体使用
    使用icon字体步骤： 
	第一步：使用font-face声明字体：
		   @font-face{
				font-family:"字体名称"；
				src:url();
		   }  
		   例如： 
		   @font-face {
            	font-family: 'iconfont';
            	src: url('font/iconfont.eot');
            	src: url('font/iconfont.eot?#iefix') format('embedded-opentype'),
            	url('font/iconfont.woff') format('woff'),
            	url('font/iconfont.ttf') format('truetype'),
            	url('font/iconfont.svg#iconfont') format('svg');
        	}
	第二步：定义使用iconfont的样式（可以结合伪元素）：
		   例如： 
	       .icon-font{
	            display: block;
	            width: 600px;
	            font-size:100px;
	            color: #000000;
	            position: relative;
	            text-align: center;
	            margin: 100px auto;
	            border: 1px solid #000;
	        }
	        /*添加伪元素，更加语义化*/
	       .icon-font::before{
	            font-family:"iconfont";
	            position: absolute;
	            content: '\e603';
	            color: red;
	            left: -11px;
	            top: 17px;
	        }
	第三步：添加定义好的样式：
		  	例如：
			<span class="icon-font">扫码支付</span>
		
	



