### 数组迭代
- v-for index
```
	<!-- v-if和v-for的综合使用 -->
	  <div id="demo1">
		  <p v-if="seen">2019年最佳影片</p>
		  <ol>
			  <li v-for="(video,index) in videos">
		        ({{index+1}}){{video.title}}/{{video.star}}
			  </li>
		  </ol>
	  </div>	
	   <script type="text/javascript">
		   <!-- v-if和v-for的综合使用 -->
		   var demo1 = new Vue({
			   el:'#demo1',
			   data:{
				   seen:true,
				   videos:[{title:'流浪地球',star:'5'},{title:'疯狂外星人',star:'4'}]
			   }
		   })
	   </script>
```
### 对象迭代
- v-for key:value
```
<div id ='demo1'>
		<ol>
			<li v-for="(value,key) in video">
				{{key}}:{{value}}
			</li>
		</ol>
	</div>
	<script type="text/javascript">
		var demo1= new Vue({
			el:'#demo1',
			data:{
				video:{
					title:'流浪地球',
					price:'100'
				}
			}
		})
		
	</script>
```
>注意这里 (value,key) 