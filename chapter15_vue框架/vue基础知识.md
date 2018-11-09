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
####4.父控件和子控件之间传值 
	1.父控件给子控件传值：父控件给子控件绑定值属性，子控件用props接受。
```javascript
      methods:{
        sendToOut:function () {
            this.$emit("inner-speak",this.toOutMsg);
          }
      }
```

2.子控件给父控件传值：父控件给子控件绑定方法监听，子控件用this.$emit("functionName",value).

```	javascript
function getPrimeNumbers(num) {
            document.writeln(num+"以内的质数有：</br>");
            for (var i=1;i<num;i++){
                var isPrime=true;
                for (var j=2;j<i;j++){
                    var temp=i%j;
                    if(temp==0){
                        isPrime=false;
                        break;
                    }
                }
                if (isPrime){
                    document.writeln(i+"</br>");
                }
            }
        }
```
