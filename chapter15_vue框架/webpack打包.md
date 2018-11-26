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