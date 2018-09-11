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
   			