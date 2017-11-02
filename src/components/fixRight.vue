<template>
	<div class="fixMain">
		<div class="fixNav" id="fixNav">
			<div class="fixItem">
				<i><img src="../assets/f1.png"></i>
				<span>京东会员</span>
			</div>
			<div class="fixItem">
				<i><img src="../assets/f2.png"></i>
				<span>购物车</span>
			</div>
			<div class="fixItem">
				<i><img src="../assets/f3.png"></i>
				<span>我的关注</span>
			</div>
			<div class="fixItem">
				<i><img src="../assets/f4.png"></i>
				<span>我的足迹</span>
			</div>
			<div class="fixItem">
				<i><img src="../assets/f5.png"></i>
				<span>我的消息</span>
			</div>
			<div class="fixItem">
				<i><img src="../assets/f6.png"></i>
				<span>咨询JIMI</span>
			</div>
		</div>
	</div>
</template>
<script type="text/javascript">
	export default{
		data(){
			return{

			}
		},
		mounted:function(){
			var fixNav = document.getElementById("fixNav");
			var item = fixNav.getElementsByTagName("i");
			var fixItem = fixNav.getElementsByTagName("span");
			for(var i=0;i<6;i++){
			    item[i].index=i;
				item[i].onmouseover = function(){
					var k = this.index;
					fixItem[k].style.transform = "translateX(-56px)";
				},
				item[i].onmouseleave = function(){
					var k = this.index;
					fixItem[k].style.transform = "translateX(0px)";
				}
			}
		}
	}
</script>
<style type="text/css">
	.fixMain{
		height:100%;
		position:fixed;
		width:6px;
		background: #7a6e6e;
		right:0;
		top:0;
		z-index: 200;
	}
	.fixNav{
		height:216px;
		width:37px;
		position: absolute;
		top:45%;
		left:-31px;
	}
	.fixItem{
		width:100%;
		height:32px;
		border-radius:3px;
		background: #7a6e6e;
		margin-top: 1px;
		padding-top: 3px;
		position: relative;
	}
	.fixItem i{
		position: absolute;
		width:100%;
		z-index: 150;
		background: #7a6e6e;
		padding-top:3px;
		margin-left: 2px;
		top:0;
		left:0;
		height:80%;
		text-align: left;
	}
	.fixItem span{
		width:60px;
		height:27px;
		position: absolute;
		left:0px;
		top:0;
		background: #7a6e6e;
		border-radius:3px;
		transition:transform .3s;
		font-size:12px;
		color:#fff;
		padding-top: 8px;
		z-index: 120;
	}
</style>