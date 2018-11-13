##常用快捷键
1.选中多处(批量编辑)：alt+J
##emmet快捷键（+TAB键） 
1.初始化：！	或者		html:5  

	缩写：html:5 或者 ！
	生成：
		<!doctype html>
		<html lang="en">
		<head>
		    <meta charset="UTF-8">
		    <title>Document</title>
		</head>
		<body>
		
		</body>
		</html>
	
2.默认单位的缩写：p----->表示% ；e----->表示em；x----->表示ex。(不写默认是px)
	
	缩写：w100 
	生成：width:100px;

	缩写：h100p
	生成：width:100%;
	
	缩写：p100e 
	生成：padding: 100em;
		
	缩写：m100x
	生成：margin: 100ex; 
3.类名、id、属性 ：.className----->表示类名；#cid----->表示id；[属性名="属性值"]----->表示属性
		
	缩写：div.className   (创建类名为className的div)
	生成：<div class="className"></div> 

	缩写：div#id 	(创建指定id的div) 
	生成：<div class="id"></div> 

	缩写：div[style="width:200px"] 	（创建一个style="width:200px"的div）
	生成：<div style="width:200px"></div> 
		 
4.后代：>----->表示后代关系 

	缩写：div>ul
	生成：<div>
	    	<ul></ul>
		 </div> 
5.兄弟节点：+----->表示兄弟关系 
	
	缩写：a+img
	生成：<a href=""></a><img src="" alt=""> 
6.提升节点：^----->表示提升该标签后面的标签，常与>结合使用，作用类似（）代替
	
	缩写：ul>li*3^ol
	生成：
		 <ul>
		    <li></li>
		    <li></li>
		    <li></li>
		</ul> 
7.分组：()----->表示括号内为一组，可以和嵌套快速生成一些代码块 

	缩写：(div.foo>h1>p)+(div.bar>h3>p) 
	生成：
		<div class="foo">
		    <h1>
		        <p></p>
		    </h1>
		</div>
		<div class="bar">
		    <h3>
		        <p></p>
		    </h3>
		</div> 
8.定义多个元素：*num----->表示定义num个重复元素 
	
	缩写：ul>li*5
	生成： 
		<ul>
		    <li></li>
		    <li></li>
		    <li></li>
		    <li></li>
		    <li></li>
		</ul>   

9.条目：item----->在不同的父元素中有不同的含义：

	a.在table中可以表示tr:
		缩写：table>tr.item*3 
		生成：
			<table>
			    <tr class="item"></tr>
			    <tr class="item"></tr>
			    <tr class="item"></tr>
			</table> 
	b.在ul或者ol中表示li:
		缩写：ol>li.item*3 
		生成： 
			<ol>
			    <li class="item"></li>
			    <li class="item"></li>
			    <li class="item"></li>
			</ol> 
	c.在select中表示option: 
		缩写：select>option.item*3 
		生成： 
		     <select name="" id="">
			    <option value="" class="item"></option>
			    <option value="" class="item"></option>
			    <option value="" class="item"></option>
			</select> 
10.填充内容：{}----->标示填充标签内容 
	
	缩写：ul>li{我是第$$个item}*3     (注意一个$表示一个占位，多个占位前面用0替换)
	生成：
		<ul>
		    <li>我是第01个item</li>
		    <li>我是第02个item</li>
		    <li>我是第03个item</li>
		</ul>

11.循环：itar----->快速生成循环代码

	缩写：itar 
	生成：			
		for (var i = 0; i < array.length; i++) { 
             var obj = array[i]; 
        }  
12.假数乱文：lorem+[num]----->可以在标签内随机生成指定num的假文,可用于快速填充内容测试效果  

	例如：lorem1000----->可以随机生成1000个单词的随机乱文

13.供应商模式：   
	
	缩写：-w ;-m ;-s ;-o
	w 表示 -webkit-
	m 表示 -moz-
	s 表示 -ms-
	o 表示 -o- 

14.meta:vp----->快速生成移动端开发meta 
		
	缩写：meta:vp 
	生成：
		<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"> 

##其他常用缩写： 
	缩写：bd+
	生成：border: 1px solid #000;

	缩写：bgc
	生成：background-color: #fff;  

	缩写：fz 
	生成：font-size:  

	缩写：fs 
	生成：font-style: italic;

	缩写：lg 
	生成：background-image: linear-gradient();

	缩写：xxx.log
	生成：console.log(xxx); 

	

