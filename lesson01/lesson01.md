[toc]
### 简介
- 第一节主要介绍一些简单的插值
### 声明式渲染
```
<!-- 第一个实例 -->
	<div id= "demo1">
		<p>{{mes1}}</p>
	</div>
	
	var demo1 = new Vue({
		el:'#demo1',
		data:({
			'mes1':'hellow Vuejs'
		})
	})
```
### 插值 v-once
- 一次赋值后无法在进行就该
```
<!-- 插值的使用 v-once -->
	<div id= 'demo2'>
		<p v-once>{{mes2}}</p>
		<p>{{mes3}}</p>
	</div>

	var demo2 = new Vue({
		el:'#demo2',
		data:({
			'mes2':'第一赋值',
			'mes3':'第一次赋值'
		})
	})
	demo2.mes2 = '第二次赋值';
	demo2.mes3 = '第二次赋值';
```
### HTML输入 v-html
- 在<>中声明v-html可在script中动态插入
```
   <div id = 'demo3'>
   	<p v-html='htmlText'> </p>
   </div>
   
   var demo3 = new Vue({
   	el:'#demo3',
   	data:({
   		'htmlText':'<font color="red">我是红色</font>'
   	})
   })
```
>> 在页面上动态的渲染html是一件很危险的事情，因为它很容易导致 XSS 攻击 (跨站脚本攻击)。

### 属性绑定 v-bind
- 要给 HTML 元素绑定属性，不能直接使用文本插值，vue 有特定的指令 【v-bind】进行属性的绑定。
```
<span v-bind:text="content">使用</span>
```
会被渲染成：
```
<span text="content">使用</span>
```
>>可省略v-bind 直接使用:+属性来代替

### JavaScript使用
- 上述介绍的几种插值方式都是简单的键值绑定，但在实际开发中，部分值要根据一些规则进行处理，这时候可以使用 JavaScript 表达式来实现。
```
	<div id ='demo5'>
		<p>{{mes4.toLowerCase()}}</p>			
	</div>
		
	var demo5 = new Vue({
		el:'#demo5',
		data:({
			'mes4':'MYAPP'
		})
	})
```
>> 使用 JavaScript 表达式进行运算时，只能使用单个表达式或者链式调用，不能使用语句。
### 过滤器
-  对于一些要经过复杂计算才显示的插值，简单的表达式可能无法满足，这时可以使用vue的过滤器进行处理。
```
  <!-- 过滤器 -->
		<div id ='demo6'>
			<p>{{mes5 | touppercase | myfilter}}</p>
		</div>

		var demo6 = new Vue({
			el:'#demo6',
			data:({
				mes5:'myapp'
			}),
			filters:({
				myfilter(value){
					return value.split('').reverse().join('');
				},
				touppercase(value){
					return value.toUpperCase();
				}
			})
		})
```
>> 上述代码中过滤器从左到右依次执行，先将插值转换成大写，然后再反转输出。
### 输入框进行数据绑定 v-model
- 使用对象
  - input 
	- select
	- textarea
	- components
```

```
