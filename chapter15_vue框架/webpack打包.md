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
		例如：
	filename:打包后文件的名称
		例如： path: 'E:\\WorkSpace\\Sublime\\H5Learn\\15_vue\\webpack-test\\dist\\js
		filename:'bundle.js',//如果是单个入口文件的话可以写死一个名称 
		filename:'[name]-[hash].js',//如果是多个入口文件的话，可以使用这样的配置，生成的打包文件时入口文件的名称【name】+当前入口文件的hash值【hash】
	publicPath:设置打包后的js的前面的绝对路径地址 
		例如：publicPath:'http://www.themelove.com'//一般项目上线时配置  
##plugin(插件)：webpack打包过程中可以用插件实现一些特殊要求，插件可以携带参数、选项，你必须在webpack配置中，向plugins属性传入new实例。 
	一般使用插件步骤：第一步（安装插件）：npm install pluginName --save-dev 
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
注意事项：插件中所有配置的参数，都可以在模板中动态获取。用法类似于模板方法。如下： 
![](https://i.imgur.com/dZntGtO.png)