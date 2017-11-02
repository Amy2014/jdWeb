<template>
	<div class="headnav">
		<el-row >
			<el-col :span="2" >
				<img class="TopPic" src="../assets/logo5.png">
			</el-col>
			<el-col :span="10" :offset="7">
				<div class="searchContent">
					<div class="searchBox">
						<div class="iconSearch" style="width:90%;float: left;">
							<input type="text" value="" >
							<i class="el-icon-picture" @click="handelIconclick"></i>
							<input type="file" id="subpic" style="opacity: 0;width:30px;overflow: hidden;">
						</div>
						<button><i class="el-icon-search"></i></button>
					</div>
					<ul>
						<li v-for="item in items"><a href="">{{item.title}}</a></li>
					</ul>
				</div>
			</el-col>
			<el-col :span="3" :offset="1" style="position:relative;margin-top:35px;z-index:10;"  class="hoverDrop" >
				<div class="shopCar">
					<el-badge :value="shopCar.length" :max="10" class="item">
						<i class="el-icon-caret-bottom"></i>
  						<span>我的购物车</span>
					</el-badge>
				</div>
				<div id="dropcarlist" class="carlist">
					<ul>
						<li v-for="(shop,index) in shopCar">
							{{index}}
							{{shop.name}}:{{shop.price}}
							<button @click="delete1(shopCar,index)">delete</button>
						</li>
					</ul>
				</div>

			</el-col>
		</el-row>
		<el-row>
			<el-col :span="13" :offset="5">
				<ul class="Topnav">
					<li><a >秒杀</a></li>
					<li><a >优惠券</a></li>
					<li><a >闪购</a></li>
					<li><a >拍卖</a></li>
				</ul>
				<span style="float:left;margin:10px;margin-top:17px;">|</span>
				<ul class="Topnav">
					<li><a >服装城</a></li>
					<li><a >京东超市</a></li>
					<li><a >生鲜</a></li>
					<li><a >全球购</a></li>
				</ul>
				<span style="float:left;margin:10px;margin-top:17px;">|</span>
				<ul class="Topnav">
					<li><a >京东经融</a></li>	
				</ul>
			</el-col>
			<el-col :span="6" >
				<a href=""><img src="../assets/topPic.png" style="margin-top:-5px;"></a>
				
			</el-col>
		</el-row>

	</div>
	
</template>
<script type="text/javascript">
	export default{
		data(){
			return{
				shopCar:[],
				input:'',
				items:[
					{title:"潮流尖货"},
					{title:"大闸蟹满减"},
					{title:"有机种植"},
					{title:"服装198减100"},
					{title:"品质家电"},
					{title:"法兰绒床垫"},
					{title:"互联网电视"}
				]
			}
		},
		created(){
			this.fetchdata();
		},
		methods:{
			handelIconclick:function(ev){
				alert("success");
			},
			drop:function(){
				var drop = document.getElementById("dropcarlist");
			},
			fetchdata:function(){
				this.$ajax.get("../static/json3").then((response)=>{
					var _this = this;
					_this.shopCar = response.data.shopCar;
				})
			},
			delete1:function(data,index){
				data.splice(index,1);
			}
		}
	}
</script>
<style type="text/css">
	.headnav{
		height:140px;	
		width:100%;
	}
	.TopPic{
		position:absolute;
		top:-30px;
		z-index:200;
		left:45px;
	}
	.searchContent{
		position:relative;
		
	}
	.el-icon-picture{
		margin-left: -20px;
		margin-top: 5px;
	}
	.searchContent ul li{
		float:left;
		list-style: none;
		font-size:10px;
		padding: 10px 5px;
		
	}
	.searchContent ul li a{
		text-decoration: none;
		color:#999;
	}
	.searchContent ul li a:hover{
		color:#f10215;
	}
	.searchBox{
		border:1px solid #f10215;
		margin-top: 25px;
		height:30px;
		text-align: left;
		background: #fff;
	}
	.searchBox input{
		height:100%;
		width:90%;
		outline:none;
		border:none;
		font-size: 18px;
		padding-left: 5px;
		float:left;
	}
	.searchBox button{
		float:right;
		height:100%;
		width:50px;
		background: #f10215;
		border:none;	
	}
	.shopCar{
		border:1px solid #ccc;
		height:31px;	
		background: #fff;
		position: relative;
		z-index: 10;
	}
	.item{
		font-size: 12px;
		padding-right: 10px;
		margin-top: 6px;
	}
	.carlist{
		width:300px;
		height:100px;
		border:1px solid #ccc;
		position:absolute;
		right:0;
		background: #fff;
		top:32px;
		display: none;
	}
	.hoverDrop:hover .carlist{
		display: block;
	}
	.hoverDrop:hover .shopCar{
		border-bottom:1px solid #fff;
	}
	.Topnav{
		margin-top: 10px;
		font-size: 16px;
		color:#333;
		font-weight: bold;
		list-style: none;
		float:left;
	}
	.Topnav li{
		float:left;
		padding:5px 13px;
	}

</style>