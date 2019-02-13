### 元素显示
- v-show
  - 标记是否显示html元素 是否添加display:none
 ```
 <div id = 'demo1'>
 	<p v-show='result'>你看到见我</p>
 	<button @click='showResult'>显示</button>
 </div>
 <script type="text/javascript">
 	var demo1 = new Vue({
 		el:'#demo1',
 		data:{
 			result:false
 		},
 		methods:{
 			showResult:function(){
 				this.result = !this.result;
 			}
 		}
 	})
 </script>
 ```