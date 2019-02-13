### 事件处理器
- v-on
```
<div id ='demo1'>
		<input id='input' v-on:keyup='txtKeyup($event)'/>
		<button id='btn' v-on:click='btnok($event)'>ok</button>
	</div>	
	<script type='text/javascript'>
		var demo1 = new Vue({
			el:'#demo1',
			methods:{
				txtKeyup:function(event){
				 this.debugLog(event)	
				},
				btnok:function(event){
				  this.debugLog(event)	
				},
				debugLog:function(event){
					console.log(
					  event.srcElement.tagName,
					  event.srcElement.id,
					  event.srcElement.innerHTML,
					  event.key?event.key:""
					)
				}
			}
			
		})
	</script>
```