####1.new 一个vue对象的时候你可以设置它的属性，其中最重要的包括data,methods,watch三个 
	data:代表vue对象的数据 
	methods：代表vue对象的方法 
	watch：设置了对象监听的方法。 
####2.vue对象里的设置通过 `html指令`	进行关联 
####3.重要的指令包括 
	渲染数据： v-text   v-html	{{}}
	控制显示： v-if(直接不渲染)	v-show（通过display:none来控制） 
	事件绑定： v-on:事件名 
例如： 		
```javascript
	 <button v-on:click="doThis"></button>
	 <button @click="doThis"></button>
``` 
	属性绑定： v-bind：属性名  
	例如：<img v-bind:src="imageSrc">
		
    循环渲染： v-for  
####4.父组件和子组件之间传值 
1.父组件给子组件传值：父组件给子组件绑定值属性，子组件用props接收。  
例如： 
父组件绑定传值 
```javascript 
    <inner-component v-bind:outMsgs="outMsgs"></inner-component> 
``` 
子组件用props接收： 
```javascript 
      export default {
      props:["outMsgs"],
    }
``` 
子组件接收后直接使用： 
```javascript 
    <ul>
      <li v-for="outMsg in outMsgs">
        {{outMsg}}
      </li>
    </ul>
```

2.子组件给父组件传值：父组件给子组件绑定方法监听，子组件用this.$emit("functionName",value)传值
例如：  
父组件给子组件绑定事件接收： 
```javascript 
    <inner-component v-on:inner-speak="receiveInnerSpeak"></inner-component> 
```  
父组件事件监听方法：
```javascript
  	components:{InnerComponent},
  	methods:{
    	//收到inner组件发来的消息
    	receiveInnerSpeak:function(msg){
      		this.innerMsgs.push(msg||"");
    	},
  	} 
```
子组件用emit传值：  
```javascript  
	methods:{
    sendToOut:function () {
         this.$emit("inner-speak",this.toOutMsg);
        }
    }
```

