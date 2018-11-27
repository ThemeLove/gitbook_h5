webpack 官网：[https://webpack.js.org/](https://webpack.js.org/)  
webpack github：[https://github.com/webpack/webpack](https://github.com/webpack/webpack)  
webpack中文文档：[https://webpack.docschina.org/concepts](https://webpack.docschina.org/concepts)

webpack:本质上，webpack 是一个现代 JavaScript 应用程序的静态模块打包器(static module bundler)。在 webpack 处理应用程序时，它会在内部创建一个依赖图(dependency graph)，用于映射到项目需要的每个模块，然后将所有这些依赖生成到一个或多个bundle。

	常用命令：
	1.npm init  初始化项目
	2.npm install webpack --save-dev:当前目录安装webpack
	3.npm install webpack-cli --save-dev:当前目录安装webpack-cli
	4.npm install webpack -g :全局安装webpack
	5.npm install webpack-cli -g :全局安装webpack-cli
	6.webpack -v :查看webpack 的版本，正常显示即表示webpack安装成功。
	7.webpack --config webpack.dev.config.js:配置webpack 的运行脚本文件
	8.package.json中配置快捷打包脚本：可以在package.json中配置快捷打包脚本属性。
		例如：如下配置之后，只需在命令行下输入 npm run webpack 即可
![](https://i.imgur.com/l46JFrs.png)

##entry(入口)
	1.单个入口写法：entry
		例如：entry:'./src/index.js'
	2.数组模式：
		例如：entry:['./index.js','./index2.js'] 
	3.对象模式：
		例如：    entry:{//对象模式
      				index:  './src/index.js',
      				hello: './src/js/hello.js'
    			 }  
##output(输出) 
	path:打包后的目录 
		例如：path: 'E:\\WorkSpace\\Sublime\\H5Learn\\15_vue\\webpack-test\\dist\\js
	filename:打包后文件的名称
		filename:'bundle.js',//如果是单个入口文件的话可以写死一个名称 
		filename:'[name]-[hash].js',//如果是多个入口文件的话，可以使用这样的配置，生成的打包文件时入口文件的名称【name】+当前入口文件的hash值【hash】
	publicPath:设置打包后的js的前面的绝对路径地址 
		例如：publicPath:'http://www.themelove.com'//一般项目上线时配置  
##plugin(插件)：webpack打包过程中可以用插件实现一些特殊要求，插件可以携带参数、选项，你必须在webpack配置中，向plugins属性传入new实例。 
	一般使用插件步骤：
				第一步（安装插件）：npm install pluginName --save-dev 
				第二部（在webpack.config.js中引入）：例如：var htmlWebpackPlugin = require('html-webpack-plugin');  
				第三部（在webpack.config.js中配置）：例如：plugins:[new pluginName({...})]
	常见用法：plugins:[
				new HtmlWebpackPlugin({
					template:'src/index.html',//使用指定的模板进行生成文件
					filename:'index-[hash].html',生成的文件名
					inject:'head',生成文件时script存放的位置，这里表示存放于head标签中
					chunk:['main'],//引用哪一个js
					minify:{
						removeComments:true,//是否删除注释
						caseSensitive:false,//是否大小写敏感
						collapseBooleanAttributes:true,////是否简写boolean格式的属性如：disabled="disabled" 简写为disabled  
						collapseWhitespace: true //是否去除空格
					}
					title:'this is custom data of title',//自定义数据，可以再模板中获取
				}),

			]  
	内置插件：path 
			使用：let path=require('path');
注意事项：插件中所有配置的参数，都可以在模板中动态获取。用法类似于模板方法。如下： 
![](https://i.imgur.com/dZntGtO.png) 

##loader:webpack中提供一种处理多种文件格式的机制，负责把各种文件格式通过不同的loader转化成浏览器认识的html、css；不同的loader有不同的配置，还可以链式配置，灵活性高。 
	一般使用loader的步骤：  
		第一步（安装loader）:
				npm install loadername --save-dev 
		第二步（在webpack.config.js中配置）：  
				module: {
					 	  rules: [
								  {test: /\.css$/, loader: "style!css?sourceMap!postcss"},
								  {test: /\.less$/, loader: "style!css!less|postcss"},
								  {test: /\.scss$/, loader: "style!css!sass|postcss"}
					 		     ]
					    }
							
							
###常用的loader 

	1.loaders之 预处理
	    css-loader 			处理css中路径引用等问题
	    style-loader 		动态把样式写入css
	    sass-loader 		scss编译器
	    less-loader 		less编译器
	    postcss-loader 		scss再处理   
		
		安装：npm install --save -dev css-loader style-loader sass-loader less-loader postcss-loader 
		
		例子：
		module: {
		 rules: [
					  {
						test: /\.css$/, //定义匹配的规则，匹配.css文件
						loader: "style!css?sourceMap!postcss"//指定用什么loader进行处理匹配到的.css文件，多个loader可以串联写，webpack的处理规则是从右往左执行。即先执行postcss----->css----->style
					  },
					  {
 						test: /\.less$/,//定义匹配的规则
						loader: "style!css!less|postcss"//指定loader处理
					  },
					  {
						test: /\.scss$/, //定义匹配的规则
						loader: "style!css!sass|postcss"//指定loader处理
					  }
		 		  ]
		}  
		
	2.loaders之 js处理
	    babel-loader
	    jsx-loader

		安装：npm install --save-dev babel-core babel-preset-es2015 babel-loader jsx-loader 
		
		 module: {
			rules: [
						 {
							test: /\.js$/, //定义匹配的规则
				            loader: "babel", exclude: /node_modules/ //指定loader处理
				    	 },
						 { 
							test: /\.jsx$/, //定义匹配的规则
						  	loader: "jsx-loader"//指定loader处理
                         }
			 		]
		} 
	
	3.loaders之 图片处理
	  	url-loader
		
	  	安装：npm install --save-dev url-loadr
		
		module: {
		   rules: [
						 {
							test: /\.(jpg|png)$/,//定义匹配的规则
						    loader: "url?limit=8192"//指定loader处理，并传参数
						 }
		  			]
		}
	

	4.loaders之 文件处理
		file-loader

		安装：npm install --save-dev file-loader
		
		module: {
		   rules: [
		  				{
						   test: /\.(png|jpg|jpeg|gif|svg|woff|woff2|ttf|eot)$/,//定义匹配的规则
						   loader: 'file'//指定loader处理
						}
		 			]
		}  

	5.loaders之 json处理
		json-loader
		
		安装：npm install --save-dev json-loader
			
		module: {
		   rules: [
		  				{
							test: /\.json$/,//定义匹配的规则
							loader: 'json'//指定loader处理
						}
		   ]
		}  
	6.loaders之 html处理
		raw-loader
		
		安装：npm install --save-dev raw-loader
			
		module: {
		 	rules: [
		  				{
						 	test: /\.html$/,//定义匹配的规则
						 	loader: 'raw'//指定loader处理
						}
		 	]
		} 

