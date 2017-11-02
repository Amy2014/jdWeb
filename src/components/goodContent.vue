<template>
	<div>
		<shortNav></shortnav>
			<div class="goodshow">
				<div class="brand">
					<img :src="good.brand">
				</div>
				<div class="gooditem">
						<img :src="good.img">
						<el-button style="margin-top: 230px;">加入购物车</el-button>
				</div>
				
			</div>
	</div>
</template>
<script type="text/javascript">
import shortNav from './shortnav';
	export default{
		data(){
			return{
				good:{}
			}
		},
		components:{
			shortNav
		},
		created(){
			this.fetchdata();
		},
		methods:{
			fetchdata:function(){
				this.$ajax.get("../static/json3").then((response)=>{
					var _this = this;
					var _index = this.$route.query.id; //获取ROUTER参数
					var data = response.data;
					if(_index <=5){
						var goods =data.group1;
						
					}
					else if(_index>5 && _index<=10){
						var goods =data.group2;
					}else{
						var goods =data.group3;
					};
					goods.forEach(function(data){  //遍历JSON数组
                    if(data.id == _index){
                       _this.good = data;
                       }
                    });

				})
			}
		}
	}
</script>
<style>
	.goodshow{
		width:100%;
		margin: 30px auto;
	}
	.brand{
		width:100%;
		text-align: center;
	}
	.gooditem{
		width:100%;
		height:400px;
		padding-top:50px;
		padding-left: 100px;
	}
	.gooditem img{
		float:left;
		height:300px;
		width:300px;
		border:1px solid #ccc;
	}
</style>