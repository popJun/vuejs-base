[toc]
### 简介
- v-if , v-for
### v-if和v-for
```
<!-- v-if和v-for的综合使用 -->
	  <div id="demo1">
		  <p v-if="seen">2019年最佳影片</p>
		  <ol>
			  <li v-for="video in videos">
		        {{video.title}}/{{video.star}}
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