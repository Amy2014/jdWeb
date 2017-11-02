<template>
	<div>	
				<div class="leftNav" id="leftNav">
					<div class="mainNav">
						<ul id="mainList">
							<li class="slide"><a href="">家用电器</a></li>
							<li>
								<a href="">手机</a>
								<span>/</span><a href="">运营商</a>
								<span>/</span><a href="">数码</a>
							</li>
							<li>
								<a href="">电脑</a>
								<span>/</span><a href="">办公</a>
							</li>
							<li>
								<a href="">家居</a>
								<span>/</span><a href="">家具</a>
								<span>/</span><a href="">家装</a>
								<span>/</span><a href="">厨具</a>
							</li>
							<li>
								<a href="">男装</a>
								<span>/</span><a href="">女装</a>
								<span>/</span><a href="">童装</a>
								<span>/</span><a href="">内衣</a>
							</li>
							<li>
								<a href="">家居</a>
								<span>/</span><a href="">家具</a>
								<span>/</span><a href="">家装</a>
								<span>/</span><a href="">厨具</a>
							</li>
							<li>
								<a href="">美妆个护</a>
								<span>/</span><a href="">宠物</a>
							</li>
							<li>
								<a href="">女鞋</a>
								<span>/</span><a href="">箱包</a>
								<span>/</span><a href="">钟表</a>
								<span>/</span><a href="">珠宝</a>
							</li>
							<li>
								<a href="">男鞋</a>
								<span>/</span><a href="">运动</a>
								<span>/</span><a href="">户外</a>
							</li>
							<li>
								<a href="">汽车</a>
								<span>/</span><a href="">汽车用品</a>
							</li>
							<li>
								<a href="">女鞋</a>
								<span>/</span><a href="">箱包</a>
								<span>/</span><a href="">钟表</a>
								<span>/</span><a href="">珠宝</a>
							</li>
							<li>
								<a href="">女鞋</a>
								<span>/</span><a href="">箱包</a>
								<span>/</span><a href="">钟表</a>
								<span>/</span><a href="">珠宝</a>
							</li>
							<li>
								<a href="">美妆个护</a>
								<span>/</span><a href="">宠物</a>
							</li>
							<li>
								<a href="">女鞋</a>
								<span>/</span><a href="">箱包</a>
								<span>/</span><a href="">钟表</a>
								<span>/</span><a href="">珠宝</a>
							</li>
							<li>
								<a href="">美妆个护</a>
								<span>/</span><a href="">宠物</a>
							</li>
							<li>
								<a href="">女鞋</a>
								<span>/</span><a href="">箱包</a>
								<span>/</span><a href="">钟表</a>
								<span>/</span><a href="">珠宝</a>
							</li>
						</ul>
					</div>
					<div class="slideRight" id="slide">
						<div name="item"  class="sitem">
							<img src="../assets/nav1.png">
						</div>
						<div name="item"  class="sitem">
							<img src="../assets/nav2.png">
						</div>
						<div name="item" class="sitem"><img src="../assets/nav3.png"></div>
						<div name="item"  class="sitem"><img src="../assets/nav4.png"></div>
						<div name="item" class="sitem"><img src="../assets/nav5.png"></div>
						<div name="item"  class="sitem"><img src="../assets/nav1.png"></div>
						<div name="item"  class="sitem"><img src="../assets/nav2.png"></div>
						<div name="item"  class="sitem"><img src="../assets/nav3.png"></div>
						<div name="item"  class="sitem"><img src="../assets/nav4.png"></div>
						<div name="item"  class="sitem"><img src="../assets/nav5.png"></div>
						<div name="item"  class="sitem"><img src="../assets/nav2.png"></div>
						<div name="item"  class="sitem">
							<img src="../assets/nav3.png">
						</div>
						<div name="item"  class="sitem">
							<img src="../assets/nav4.png">
						</div>
						<div name="item"  class="sitem">
							<img src="../assets/nav5.png">
						</div>
						<div name="item"  class="sitem">
							<img src="../assets/nav1.png">
						</div>
						<div name="item"  class="sitem">
							<img src="../assets/nav2.png">
						</div>
					</div>
				</div>
	</div>
	
</template>
<script type="text/javascript">
	export default{
		data () {
			return{
				
			}
		},
		mounted:function(){
			var main = document.getElementById("leftNav");
			var f=document.getElementById("mainList");
			var son = f.getElementsByTagName("li");
			var slide = document.getElementById("slide");
			var slideList = document.getElementsByClassName("sitem");
			var count1 = son.length;
			var count2 = slideList.length;
			f.onmouseover = function(){
				slide.style.display = "block";
			}
			main.onmouseleave = function(){
				slide.style.display = "none";
				for(var i=0;i<count1;i++){
					son[i].style.background="#6e6568";
				}
			}
			for(var i=0;i<count1;i++){
				son[i].index=i;
				son[i].onmouseover = function(){
					var k=this.index;
					slideList[k].style.display="block";
					son[k].style.background="#999";
					for(var j=0;j<count2;j++){
						if(j!=k){
							slideList[j].style.display="none";
							son[j].style.background="#6e6568";
						}
					}
				}

			}
		}
	}
</script>
<style type="text/css">
	.leftNav{
		position:absolute;
		top:0;
		left:45px;
		background: #6e6568;
		z-index: 50;
	}
	.mainNav{
		width:188px;
		height:450px;
		color:#fff;
		padding:15px 0px;
		text-align: left;
		font-size: 14px;
		position: relative;
	}
	.mainNav a{
		text-decoration: none;
		color:#fff;
	}
	.mainNav a:hover{
		color:red;
	}
	.mainNav ul{
		list-style: none;
	}
	.mainNav >ul >li{
		height:18px;
		padding:5px 12px;
		padding-right: 0;
	}
	.mainHover{
		background: #999;
	}

	.mainNav ul li a{
		display: inline-block;
	} 
	.mainNav ul li span{
		padding-top: 2px;
		margin:0 3px;
		
	}
	.slideRight{
		border:1px solid #EEE;
		box-shadow: 1px -1px 5px #999;
		width:998px;
		min-height:480px;
		position:absolute;
		left:188px;
		top:0;
		display:none;
		background: #f6f6f6;
	}
	.slideRight > div{
		background: #f6f6f6;
		display: none;
	}
</style>