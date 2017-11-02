<template>
	<div>
		<el-row class="short-nav"style="background-color: #e3e4e5;height:30px;width:100%;font-size: 12px; z-index: 100;" >
			<el-col :span="2" :offset="4" style="position:relative;padding-left:30px;">
				<div  @mouseenter="show('drop','itemShow')" @mouseleave="show('drop','itemShow')">
					<div class="show-item"  id="itemShow">
						<i class="el-icon-caret-bottom"></i>
						<span v-for="city in citys" v-if="city.choosen" id="curName">{{city.name}}</span>
					</div>
					<div class="drop-layer" id="drop">
						<ul>
							<li v-for="city in citys" v-bind:class="{choosen: city.choosen }" @click="change($event,citys)">{{city.name}}</li>
						</ul>
					</div>
				</div>
				
			</el-col>
			<el-col :span="2" :offset="3">
				<a href="	" >你好，请登录</a>
			</el-col>
			<el-col :span="1" >
				<a href="	" style="color:red">免费注册</a>
			</el-col>
			<el-col :span="2" >
				
				<span class="alist">
					<span style="margin-right: 10px;">|</span>
					<a href="	">我的订单</a>
				</span>
			</el-col>
			<el-col :span="2" style="margin-left: -22px;position:relative;">	
					<div class="alist" @mouseenter="show('drop-1','show-1')" @mouseleave="show('drop-1','show-1')">
						<span style="margin-right: 10px;">|</span>
						<a href="	" id="show-1">
								<span>我的京东</span>
							    <i class="el-icon-arrow-down"></i>
						</a>
						<div id="drop-1" class="drop1">
							<ul class="drop-list">
								<li v-for="dlist in dropList">{{dlist.name}}</li>
							</ul>
						</div>
						
					</div>
			
			</el-col>

			<el-col :span="2" style="margin-left: -25px;">
				<span class="alist">
					<span style="margin-right: 10px;">|</span>
					<a href="	">京东会员</a>
				</span>
			</el-col>
			<el-col :span="2" style="margin-left: -27px;">	
				<span class="alist">
					<span style="margin-right: 10px;">|</span>
					<a href="	">企业采购</a>
				</span>
			</el-col>
			<el-col :span="2" style="margin-left: -25px;position:relative;">
				
				<div class="alist" @mouseenter="show('drop-2','show-2')" @mouseleave="show('drop-2','show-2')">
					<span style="margin-right: 10px;">|</span>
						<a href="	" id="show-2">
						
								<span>客户服务</span>
							    <i class="el-icon-arrow-down"></i>		
						</a>
						<div id="drop-2" class="drop2">
							<ul class="drop-list">
								<li v-for="dlist in dropList">{{dlist.name}}</li>
							</ul>
						</div>
						
				</div>
			</el-col>
			<el-col :span="2" style="margin-left: -18px;position:relative;z-index: 10;">
				<div class="alist" @mouseenter="show('drop-3','show-3')" @mouseleave="show('drop-3','show-3')">
					<span style="margin-right: 10px;">|</span>
						<a href="	"id="show-3">
							
								<span>网站导航</span>
							    <i class="el-icon-arrow-down"></i>
							
						</a>
                    <span style="margin-left:3px;">|</span>
						<div id="drop-3" class="drop2">
							<ul class="drop-list">
								<li v-for="dlist in dropList">{{dlist.name}}</li>
							</ul>
						</div>
						
				</div>
			</el-col>
			<el-col :span="2"  style="margin-left: -21px;position:relative;">
				<div class="alist" @mouseenter="show('drop-4','show-4')" @mouseleave="show('drop-4','show-4')">
					
						<a href="	" id="show-4">
							
								<span>手机京东</span>

								<img src="../assets/logo1.png" style="margin-top:10px;position:absolute;left:15px;">
					
						</a>
						<div id="drop-4" class="drop4">
							<img src="../assets/logo2.png" style="margin-top:10px;">
							<hr>
							<img src="../assets/logo3.png" style="margin-top:10px;"> 
							<hr>
							<img src="../assets/logo4.png" style="margin-top:10px;">
						</div>
						
				</div>
			</el-col>
		</el-row>
	</div>
</template>
<script type="text/javascript">
	export default{
		data(){
			return{
				citys:[
				{name:"北京",choosen:false},
				{name:"上海",choosen:false},
				{name:"天津",choosen:true},
				{name:"辽宁",choosen:false},
				{name:"山东",choosen:false},
				{name:"重庆",choosen:false},
				{name:"河北",choosen:false},
				{name:"哈尔滨",choosen:false},
				],
				dropList:[
					{name:"待处理订单"},
					{name:"消息"},
					{name:"返修退换货"},
					{name:"我的订单"},
					{name:"降价商品"},
					{name:"我的关注"},
					{name:"我的京豆"},
					{name:"我的理财"},
					{name:"我的优惠券"},
					{name:"我的白条"}
					]
				}
			},
		
		created:function(){
			var items = document.getElementsByTagName("li");
			var count = items.length;
			for(var i=0;i<count;i++){
				items[i].key = i; 
				items[i].onmouseover = function(){
					index=this.key;
					alert(index);
				}
			}
		},
		methods:{
			show:function(dropid,itemShowid){
				var drop = document.getElementById(dropid);
				var item = document.getElementById(itemShowid);
				if(drop.style.display=="block"){
					drop.style.display ="none";
					item.style.background = "#e3e4e5";
					item.classList.remove("show-item-hover");
				}
				else{
					drop.style.display="block";
					item.style.background = "#fff";
					item.classList.add("show-item-hover");
				}
				
			},
			change(event,citys){ //获取事件本身元素 $event
				var items = document.getElementsByTagName("li");
				var count = items.length;
				var dom = event.target;
				for( var i=0;i<count;i++){
					if(items[i]==dom){
						citys[i].choosen=true;
					}
					else{
						citys[i].choosen=false;
					}
				}
			}
		}
	}
</script>
<style type="text/css">
	.short-nav{
	background-color: #e3e4e5;
	height:30px;
	font-size: 12px;
	}
	.short-nav a{
		text-decoration: none;
		color:#666;
		height:24px;
		display: inline-block;
		padding-top: 6px;
	}
	.short-nav a:hover{
		color:red;
	}
	.show-item{
		height:25px;
		padding-top: 5px;
		color:#666;
		width:70px;
	}
	.show-item-hover{
		border-left:1px solid #ccc;
		border-right:1px solid #ccc;
	}

	.drop-layer {
		position:absolute;
		width:200px;
		height:200px;
		top:30px;
		left:30px;
		background-color: #fff;
		display:none;
		border:1px solid #ccc;
		border-top:none;
	}
	.drop-layer ul {
		list-style: none;
	}
	.drop-layer ul li{
		width:40px;
		margin-top:8px;
		margin-bottom: 8px;
		float:left;
	}
	.drop-layer ul li:hover{
		color:red;
		background: #e3e4e5;
	}
	.drop-layer ul li a{
		text-decoration: none;
	}
	.choosen{
		background: red;
		color:#fff;
	}
	.alist{
		padding-right:13px;
		display: inline-block;
		overflow: hidden;
	}
	.drop1{
		border:1px solid #ccc;
		border-top:none;
		width:300px;
		height:190px;
		position:absolute;
		top:30px;
		left:21px;
		display:none;
		background: #fff;
		color:#999;
	}
	.drop2{
		border:1px solid #ccc;
		border-top:none;
		width:300px;
		height:190px;
		position:absolute;
		top:30px;
		right:20px;
		display:none;
		background: #fff;
		color:#999;
	}
	.drop4{
		border:1px solid #ccc;
		border-top:none;
		width:200px;
		height:350px;
		position:absolute;
		top:30px;
		right:10px;
		display:none;
		background: #fff;
		color:#999;
	}
	.drop-list{
		float:left;
		padding-top: 20px;
	}
	.drop-list li{
		list-style: none;
		width:140px;
		line-height:30px;
		float:left;
		text-align: left;
		padding-left: 10px;
	}
	.drop-list li a{
		margin:0;
		padding:0;
	}
</style>