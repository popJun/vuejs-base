[toc]
### 简介
- 主要介绍计算属性,处理元数据
### computed的使用
```
    <div id='demo1'>
		a = {{a}}
		b = {{b}}
	</div>
	
	<!-- js -->	
	<script type="text/javascript">
		<!-- computed的使用 -->
		var demo1 =new Vue({
			el:'#demo1',
			data:{
				a : 1
			},
			computed:{
				b:function(){
					//当没有指明是默认调用computed中的get
					return this.a +1;
				}
			}
		})
		//无法改变
		demo1.b = 8
		//b随着a的改变而改变
		demo1.a = 8
	</script>
```

>>由于b和a绑定所以外部无法改变b的值，b随着a的改变而改变 ,需要设置set函数
>>在没有设置set函数的情况下控制台会打印警告
- computed get和set方法的使用
```
   <div id = 'demo2'>
	   	{{mes2}}
   </div>
   
   var demo2 = new Vue({
   	el:'#demo2',
   	data:{
   		title: 'my first lesson'
   	},
   	computed:{
   		mes2:{
   		get:function(){
   			return this.title;
   		},
   		//没有加set mes2值无法改变
   		set:function(newValue){
   				this.title = newValue;
   		}
   		}				   
   	}
   })
   demo2.mes2='my sesson lesson';
```
>>没有对set进行定义时mes2自行改变 --只能改变title的值才会改变
### methods方法（被动改变）
```
    <!-- method的使用 -->
	<div id ='demo3'>
		<p>{{mes3}}</p>
		<button v-on:click='reverseMes'>逆转消息</button>
	</div>
	/* method的使用 */
	var demo3 = new Vue({
		el:'#demo3',
		data:{
			mes3:'hello VueJs'
		},
		methods:{
			reverseMes:function(){
				this.mes3 = this.mes3.split('').reverse().join('')
			}
		}
	})	
```
### watch 观察者 （主动改变）
- watch 属性用于监视 vue 实例上的数据变动，并相应的改变其他变量的值。
```
    <!-- watch的使用 -->
	<div id ='demo4'>
		<input type='text' v-model='firstName'>
		<input type='text' v-model='lastName'>
		<p>我的名字是：{{fullName}}</p>
	</div>
    <!-- watch的使用 -->
	  var demo4 = new Vue({
		  el:'#demo4',
		  data:{
			firstName:'wu',
			lastName:'shaochuan',
			fullName:'wu shaochuan'
		  },
		  watch:{
			  firstName:function(curVal, oldVal){
				  this.fullName = curVal + " " + this.lastName;
			  },
			  lastName:function(curVal,oldVal){
				  this.fullName = this.firstName + " " + curVal;
			  }
			}
	  })		
```
