#### 	
	1.浮动和定位会使元素脱离标准流，可以让原来不是块级元素的元素变成块级元素，可以给它们设置宽高，由于脱离了标准流，所以它们不占用空间，所以它们不参与父盒子的宽高计算，不能撑开父盒子。除非给它们的父盒子清除浮动。
####2.margin的合并： 
	2个相邻的上下盒子之间如果都设置了margin,比如上盒子设置了margin-bottom:100px,下盒子设置了margin-top:50px,最终2个盒子之间的margin值为100px;浏览器会取2者中的最大值作为最终值。
	要解决这个问题，最常用的办法就是给父盒子添加overflow:hidden属性。 
####3.属性的继承（有些属性可以继承，有些属性不能继承）
	可以继承的属性：text-align
	例如：比如text-align,比如li>a>img+p这种布局，给li设置了 
		 text-align属性,那么a标签也就继承了这种属性，其中的img和p也都会水平居中。 
	不可以继承的属性：display 
	例如：display,比如div>a>img+p这种布局，给a标签设置宽高没有用，因为a不是块级元素，即使它的父级元素是div是块级元素（display:block）,也不行；需要手动给a添加display:block,设置的宽高才有效。 

####4.使用js添加的样式为行内式样式，可以通过审查元素查看。
####5.touchstart、touchmove、touchend是移动端特有事件。
####6.webkitTransitionEnd :添加过渡结束事件，该事件是C3新添加事件，需要添加浏览器私有化前缀.
####7.white-space:nowrap :可以让内容在一行，不换行
####8.让子控件顶端对齐可以让设置父控件font-size:0,让后在给要对齐的子控件这种display:inline-block,vertical-align:top 
####9.window.location对象包含有关当前URL信息，属性包括：
	hash 	设置或返回从井号 (#) 开始的 URL（锚）。
	host 	设置或返回主机名和当前 URL 的端口号。
	hostname 	设置或返回当前 URL 的主机名。
	href 	设置或返回完整的 URL。
	pathname 	设置或返回当前 URL 的路径部分。
	port 	设置或返回当前 URL 的端口号。
	protocol 	设置或返回当前 URL 的协议。
	search 	设置或返回从问号 (?) 开始的 URL（查询部分） 
####10.Vue动态添加可追踪的响应式属性：（Vue不允许在已经创建的实例上动态添加新的根级响应式属性，要想属性被追踪，要在组件data中声明，不然普通方法动态添加属性，不能被追踪）。
	然而可以使用 ：
	Vue.set(object,key,value)方法将响应属性添加到实例上,Vue.set(vm.someObject,"b",2)； 
	您也可以使用vm.$set实例方法，这也是全局Vue.set方法的别名。this.$set(this.someObject,"b",2);	
####11.Object.assign() 或 _.extend() 方法来添加属性，可以向已有对象添加多个属性，但是，这样添加到对象上的新属性不会触发更新。在这种情况下可以创建一个新的对象，让它包含原对象的属性和新的属性：
	// 代替 `Object.assign(this.someObject, { a: 1, b: 2 })`
		this.someObject = Object.assign({}, this.someObject, { a: 1, b: 2 })
####12.keep-alive是Vue内置的一个组件，可以使被包含的组件保留状态，或者避免重新渲染。
	a.普通用法：
		<keep-alive>
		  <component>
		    <!-- 该组件将被缓存！ -->
		  </component>
		</keep-alive>

	b.结合include和exclude属性：
		include-字符串或正则表达式，只有匹配的组件会被缓存
		exclude-字符串或正则表达式，任何匹配的组件都不会被缓存
		
		//组件 a
		export default {
		  name: 'a',
		  data () {
		    return {}
		  }
		}
	
		<keep-alive include="a">
		  <component>
		    <!-- name 为 a 的组件将被缓存！ -->
		  </component>
		</keep-alive>可以保留它的状态或避免重新渲染
		
		
		<keep-alive exclude="a">
		  <component>
		    <!-- 除了 name 为 a 的组件都将被缓存！ -->
		  </component>
		</keep-alive>可以保留它的状态或避免重新渲染

	
	c.结合vue-router的用法
		router-view也是一个组件，如果直接被包在keep-alive里面，所有路径匹配到的视图组件都会被缓存：
		
		<keep-alive>
		    <router-view>
		        <!-- 所有路径匹配到的视图组件都会被缓存！ -->
		    </router-view>
		</keep-alive>

