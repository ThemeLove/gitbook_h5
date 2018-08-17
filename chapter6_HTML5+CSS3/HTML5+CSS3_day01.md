####1.html5是html4的升级版；广义的概念：代表着浏览器技术发展的一阶段，HTML5+CSS3+js API一套前端技术的组合。
	特点：1.文档结构更简洁、书写更宽松 
		 2.新增语义化标签： 
		   <nav>标示导航 
		   <header>表示页眉 
		   <footer>表示页脚 
		   <section>表示区块 
		   <article>表示文章、帖子、评论、博客等 
		   <aside>表示侧边栏 如文章的侧边栏 
		   <figure>标示媒介内容分组 注意 ul>li的比较  
		   <mark>表示标记（带用"UI",不怎么用）
		   <progress>表示进度（带用"UI"，不怎么用） 
           <time>标示日期
####2.标签语义化：在合适的地方用合适的标签，对搜索引擎seo优化有好处
	p：段落   h1:标题
	div:可以放任何东西  
####3.IE8以下不兼容htm5的新标签。 
	实际开发过程中可以通过检查IE版本来加载第三方的一个JS库来解决兼容问题，实际原理是将新标签全部通过 
	document.createElement('tagName')来创建一遍。如下： 

	条件注释,如果满足条件就执行，不满足条件就注释：
	<!--[if lte IE 8]> 
		<script src="./js/html5shiv.min.js"></script> 
	<![endif]-->  
	l:less 		更小
	t:than 		比
	e:equals 	等于
	g:great		更大
	
####4.html5新增表单属性type类型 
	email     邮箱格式
	color 	  拾色器
	url 	  只能输入url格式
	number 	  只能输入数字
	range 	  范围，滑动条
	tel 	  号码
	search    搜索框
	time      时间
	date      日期
	week 	  周
	month	  月 

####5.html5新增表单元素 
	datalist    数据列表标签,input输入框属性list指定datalist的id,组合可以做下拉选择菜单
    output      输出
    keygen      加密
    meter       度量器 属性value、min、max、low、high,当value小于low或高于high时，会显示警告色
    progress    进度条 

####6.html5新增表单属性 
	placeholder		提示文字（占位符） 
	autofocus		自动获取焦点，属性值和属性名相同时，可以不写属性值
	autocomplete	自动匹配已经输入的内容，on(默认开启)，off 关闭 
	required	    必填项，空值会提示 
	multiple		多选 
	novalidata		关闭表单自动验证功能（只能加给form） 
    pattern			正则表达式
	
####7.html5新增表单事件 
    oninput        当用户输入的时候触发
    oninvalid      当验证不通过时触发，可用于设置提示文字 this.setCustomValidity("提示文字")