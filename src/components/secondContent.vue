<template>
	<div class="secMain" >
		<div class="secTop">
			<el-row style="padding:5px;" >
				<el-col :span="4">
					<img src="../assets/title1.png">
				</el-col>
				<el-col :span="4" style="padding-top:17px;margin-left:-40px;">
					<a href="">总有你想不到的低价
						<i class="el-icon-caret-right"></i></a>
				</el-col>
				<el-col :span="7" :offset="9" style="padding-top:10px;">
					<span style="color:#fff">当前场次</span>
					<span  class="time"></span>
					<i class="el-icon-minus"></i>
					<span  class="time"></span>
					<i class="el-icon-minus"></i>
					<span  class="time"></span>
					<span style="color:#fff">后结束抢购</span>
				</el-col>
		</el-row>
		<div class="secShow">
			<el-row>
				<el-col :span="19" style="width:1000px;">
					<el-carousel indicator-position="none" :autoplay="false">
						<el-carousel-item>
							<ul class="gList">
								<li v-for="good in goodsList1">
									<a  @click="goList(good.id)">
										<img :src="good.img">
										<p>{{good.alt}}</p>
									</a>
									<p >
										<span class="pNow"><i>￥</i>{{good.priceNow}}.00</span>
										<span class="pPre"><i>￥</i>{{good.pricePre}}.00</span>
									</p>
								</li>
							</ul>
						</el-carousel-item>
						<el-carousel-item>
							<ul class="gList">
								<li v-for="good in goodsList2">
									<a href="">
										<img :src="good.img">
										<p>{{good.alt}}</p>
									</a>
									<p >
										<span class="pNow"><i>￥</i>{{good.priceNow}}.00</span>
										<span class="pPre"><i>￥</i>{{good.pricePre}}.00</span>
									</p>
								</li>
							</ul>
						</el-carousel-item>
						<el-carousel-item>
							<ul class="gList">
								<li v-for="good in goodsList3">
									<a href="">
										<img :src="good.img">
										<p>{{good.alt}}</p>
									</a>
									<p >
										<span class="pNow"><i>￥</i>{{good.priceNow}}.00</span>
										<span class="pPre"><i>￥</i>{{good.pricePre}}.00</span>
									</p>
								</li>
							</ul>
						</el-carousel-item>
					</el-carousel>
				</el-col>
				<el-col :span="3">
					<img src="../assets/ad1.jpg">

				</el-col>
			</el-row>
		</div>
		</div>
	</div>
</template>
<script type="text/javascript">
	export default{
		data(){
			return{
				goodsList1:[],
				goodsList2:[],
				goodsList3:[]
			}
		},
		created(){
			this.fetchDate();
		},
		mounted(){
			this.set=setInterval(function(){
				var timeBox = document.getElementsByClassName("time"); //***倒计时函数实现
				var setTime = new Date(2017,10,24,12,55,10);
				var leftime = setTime-(new Date());
				var hour = parseInt(leftime / 1000 / 60 / 60 % 24);
				var minute = parseInt(leftime/1000/60%60);
				var second = parseInt(leftime/1000%60);
				timeBox[0].innerHTML = hour;
				timeBox[1].innerHTML = minute;
				timeBox[2].innerHTML = second;
				},1000);
		},
		beforeDestroy() {

      		clearInterval(this.set);  //清除SETiNTERVAL事件
      		//window.clearInterval(timer1)  官方
   		 },
		methods:{
			fetchDate:function(){
				this.$ajax.get("../static/json3").then((response)=>{
						var group1 = response.data.group1;
						var group2 = response.data.group2;
						var group3 = response.data.group3;
						var _this = this;
						_this.goodsList1 = group1;
						_this.goodsList2 = group2;
						_this.goodsList3 = group3;

				})
			},
			goList:function(goodid){
				this.$router.push({name:'goods',query:{id: goodid} }); 
				//query实现router跳转后参数不消失
			}
		}
	}
</script>
<style type="text/css">
	.secMain{
		width:1185px;
		height:305px;
		margin-top: 10px;
		margin-left: 45px;
		position:relative;
		background: #fff url(../assets/bg11.png) no-repeat;
	}
	.secMain a{
		text-decoration: none;
		color:#fff;
		font-size: 14px;
	}
	.secTop{
		background:url(../assets/bg1.png) no-repeat;
		height:55px;
	}
	.time{
		border-radius:10px;
		background: #440106;
		height:30px;
		width:35px;
		color:red;
		display: inline-block;
		padding-top:10px;
		margin-top: -7px;
		font-size:20px;
		font-weight: bold;
	}
	.secShow{
		height:225px;
		padding-right: 13px;
	}
	.gList{
		list-style: none;
	}
	.gList a{
		height:176px;
		width:170px;
		text-decoration: none;
		color:#999;
		display: inline-block;
		padding-top: 10px;
	}
	.gList a:hover{
		color:red;
	}
	.gList a img{
		transition: transform .3s;
	}
	.gList a:hover img{
		transform:translateY(-5px);
	}
	.gList a p{
		width:179px;
		height:32px;
		margin:0 auto;
		font-size: 12px;
		text-align: left;
		overflow: hidden;
		line-height: 16px;
		word-wrap: break-word;
    	word-break: break-all;
	}
	.gList li{
		width:178px;
		height:225px;
		padding:0 10px;
		float:left;
		border-right: 1px solid #eee
	}
	.gList li p{
		text-align: left;
	}
	.pNow i{
		font-size: 12px;
		margin-right: 5px;
	}
	.pNow{
		font-size: 20px;
		color:red;
		font-weight: bold;
	}
	.pPre{
		margin-left: 10px;
	}
	.pPre i{
		text-decoration: none !important;
		margin-right: 5px;
	}
	.pPre{
		font-size:12px;
		color:#999;
		text-decoration: line-through;
	}
	.el-carousel__arrow{
		top:30% !important;
	}
</style>