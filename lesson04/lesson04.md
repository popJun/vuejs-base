### 简介
- 组件（component） ：定义页面的区域块。
- 自定义一个html标签
```
    <div id = 'demo1'>
		<video-item v-for='item in videos' v-bind:video='item'></video-item>
	</div>
	<script type="text/javascript">
		Vue.component('video-item',{
			props:['video'],
			template:'<li>{{video.title}}</li>'
		})
		var demo1 = new Vue({
			el:'#demo1',
			data:{
				videos:[{title:'流浪地球'},{title:'疯狂外星人'}]
			}
		})
	</script>
```