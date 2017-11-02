<template>
	<div class="mainCon">
		<leftNav></leftNav>
		<div class="scoPic">
			<el-carousel height="340px">
				<el-carousel-item>
					<a href="">
						<img src="../assets/1.jpg">
					</a>
				</el-carousel-item>
				<el-carousel-item>
					<a href="">
						<img src="../assets/2.jpg">
					</a>
				</el-carousel-item>
				<el-carousel-item>
					<a href="">
						<img src="../assets/3.jpg">
					</a>
				</el-carousel-item>
				<el-carousel-item>
					<a href="">
						<img src="../assets/4.jpg">
					</a>
				</el-carousel-item>
				<el-carousel-item>
					<a href="">
						<img src="../assets/5.jpg">
					</a>
				</el-carousel-item>
			</el-carousel>
			<div class="picBot">
				<a href="">
					<img src="../assets/b1.png">
				</a>
				<a href="">
					<img src="../assets/b2.png">
				</a>
			</div>
		</div>
		<rightItem></rightItem>
	</div>
	
</template>
<script >
	import leftNav from './leftNav';
	import rightItem from './rightItem';
	export default{
		components:{
			leftNav,
			rightItem
		}
	}
</script>
<style type="text/css">
	.mainCon{
		width:100%;
		height:480px;
		position:relative;
	}
	.scoPic{
		background: #f6f6f6;
		width:790px;
		margin-left:243px;
		float:left;
	}
	.picBot{
		height:130px;
		width:100%;
		margin-top: 8px;
	}
</style>