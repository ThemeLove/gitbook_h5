##-------------------------------上午-------------------------------   
####1.多媒体 （audio/video）
	标签：figure:多媒体
	     figcaption:多媒体标签 
	方法：load() 加载、play()播放、pause()暂停 
	属性：currentTime 视频播放的当前进度 
	     duration:视频的总时长 
	     paused:视频播放状态 暂停状态 
	事件：oncanplay:事件在用户可以开始播放音频/视频（audio/video）时触发。 
	     ontimeupdate:通过该事件来报告当前的播放进度
		 onended:播放完成时触发 
	
	全屏：video.webkitRequestFullScreen(); 
####2.拖拽 （在HTML5的规范中，我们可以通过为元素增加draggable="true"来设置此元素是否可以进行拖拽操作，其中图片、链接默认是开启的 ）
	拖拽元素：页面中设置了draggable="true"属性的元素 
	目标元素：页面中任何一个元素都可以成为目标元素 
	拖拽事件监听：
	    拖拽元素：
				ondrag:应用于拖拽元素，整个拖拽过程都会调用 
		    	ondragstart:应用于拖拽元素，当拖拽开始时调用 （按下鼠标开始拖拽）
				ondragend:应用于拖拽元素，当拖拽结束时调用（松开鼠标）  
				ondragenter:应用于拖拽元素时，当拖拽开始时调用 （按下鼠标开始拖拽，晚于ondragstart） 
				ondragleave:应用于拖拽元素时，当拖拽元素离开自身时调用（以鼠标指针为判断依据）
		目标元素：
				ondragenter:应用于目标元素，当拖拽元素进入时调用，以鼠标指示为判断依据 
				ondragover:应用于目标元素，当拖拽元素停留在目标元素上时调用 
				ondragleave:应用于目标元素，当拖拽元素离开目标元素时调用，以鼠标指示为判断依据 
				ondrop:应用于目标元素，当拖拽元素在目标元素上松开鼠标时调用  

##-------------------------------下午-------------------------------    
####3.全屏模式（任何元素）  
	HTML5规范允许用户自定义网页上任一元素全屏显示。
	 	requestFullscreen() 开启全屏显示
	 	cancleFullscreen() 关闭全屏显示
	不同浏览器需要添加前缀如：
	 	webkitRequestFullScreen、mozRequestFullScreen
	 	webkitCancleFullScreen、mozCancleFullScreen
	通过document.fullScreen检测当前是否处于全屏
	不同浏览器需要添加前缀
	    document.webkitIsFullScreen、document.mozFullScreen
	全屏伪类
		:full-screen {}、:-webkit-full-screen {}、:moz-full-screen {} 
	例如：
		.box::full-screen{
			background-color:red;//.box 全屏状态下背景变为红色
		}
			
####4.web存储 
	sessionStorage:session(会话，会议) 5M 当前窗口关闭时数据销毁，在内存中。
	localStorage:20M 永久生效，除非手动删除，清理垃圾，否则始终在硬盘上。 
####5.监听网络状态
    window.onload=function (ev) {
        window.onload=function (ev) {
            window.addEventListener("online",function (ev2) {
                alert("网络已连接");
            });
            window.addEventListener("offline",function (ev2) {
                alert("网络已断开");
            });
    }; 
####6.应用缓存 
	清单文件:.appcache
	格式：		
		CACHE MANIFEST
	
		#注释以#号开头,缓存前三张图片
		CACHE:
			../images/img1.jpg
			../images/img2.jpg
			../images/img3.jpg
			../images/img4.jpg
		
		#指定必须联网才能访问的图片
		NETWORK:
			http://img2.mukewang.com/szimg/5ab84f650001f0b005400300.jpg
		
		#当页面无法访问时回退时的页面
		FALLBACK:
			404.html
例如：
![.appcache文件](https://i.imgur.com/KIfEXKV.png) 

####7.地理定位(常用获取地理定位的方式：IP、GPS、WIFI、手机信号)
	navigator.geolocation.getCurrentPosition（successCallback,errorCallback）； 
    navigator.watchPosition(successCallback, errorCallback, options) 重复获取当前地理信息
    1、当成功获取地理信息后，会调用succssCallback，并返回一个包含位置信息的对象position。Coords(坐标)
    position.coords.latitude纬度
    position.coords.longitude经度
    2、当获取地理信息失败后，会调用errorCallback，并返回错误信息error
    3、可选参数 options 对象可以调整位置信息数据收集方式
例如： 
![geolocation定位](https://i.imgur.com/Atj47f4.png)