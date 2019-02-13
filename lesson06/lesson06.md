###简介
- v-bind:class
### v-bind:class
- 为html标记绑定样式class属性
```
 <div id ='demo1'>
		  <p v-bind:class="{divcolor:iscolor}">我是红色</p>
		  <p :class="{divcolor:iscolor}">我是红色</p>
          <button @click='changeColor'>改变class</button>
	  </div>
	  <script type="text/javascript">
		  var demo1 = new Vue({
			  el:'#demo1',
			  data:{
				  iscolor:true
			  },
			  methods:{
				  changeColor:function(){
					  this.iscolor = !this.iscolor;
				  }
			  }
		  })
	  </script>	  
```

### class的对象绑定
- 为html标记绑定样式class对象
```
    <!-- 为class绑定对象 -->
    <div id = 'demo2'>
    	<p :class='myclass'>我是红色</p>
    	<button @click='changeColor'>改变class</button>
    </div>
	<!-- 为class绑定对象 -->
	var demo2 = new Vue({
		el:'#demo2',
		data:{
			myclass:{
				pcolor:true
			} 
		},
		methods:{
			changeColor:function(){
				this.myclass.pcolor = !this.myclass.pcolor;
			} 
		}
	})
```