<template>
	<div class="rightMain">
		<div class="Rtop">
			<div class="userMsg">
				<div v-if="user">
					{{user.name}}
				</div>
				<div v-if="!user" style="margin-top:15px;height:75px; ">
					<div class="headPortrait">
						<img src="../assets/no_login.jpg">
					</div>
					<div>
						<p style="padding:6px 0;">Hi,欢迎来到京东!</p>
						<a class="amsg" href="">登录</a>
						<a class="amsg" href="">注册</a>
					</div>
				</div>
				<div>
					<a href="" class="abutton">
						新人福利
					</a>
					<a href="" class="abutton" style="margin-left:10px;">
						PLUS会员
					</a>
				</div>
			</div>
		</div>
		<div class="Rmid">
			<div class="tab" id="tab" style="position:relative;">
				<ul>
					<li >促销</li>
					<li style="border-left:1px solid #ccc">公告</li>
					<span><a href="">更多</a></span>
				</ul>
				<span class="tab_roll" id="roll"></span>	
			</div>
			<div class="tabHover">
				<div id="tab1">
					<ul>
						<li><a href="">家纺跨店满199减40</a></li>
						<li><a href="">每日享折扣，京东品质游</a></li>
						<li><a href="">家纺跨店满199减40</a></li>
						<li><a href="">家纺跨店满199减40</a></li>
					</ul>
				</div>
				<div id="tab2" style="display:none;">
					<ul>
						<li><a href="">京东扶贫频道正式上线运营</a></li>
						<li><a href="">每日享折扣，京东品质游</a></li>
						<li><a href="">家纺跨店满199减40</a></li>
						<li><a href="">家纺跨店满199减40</a></li>
					</ul>
				</div>
			</div>
		</div>
		<div class="Rbot">
			<div class="ishow">
				<ul id="ishow">
					<li style="border-top:none;border-left: none;" @mouseenter="slideup(0)">
						<a href="">
							<img src="../assets/i1.png">
							<span class="ispan">话费</span>
						</a>
						
					</li>
					<li style="border-top:none;" @mouseenter="slideup(1)">
						<a href="">
							<img src="../assets/i2.png">
							<span class="ispan">机票</span>
						</a>
					</li>
					<li style="border-top:none;" @mouseenter="slideup(2)">
						<a href="">
							<img src="../assets/i3.png">
							<span class="ispan">酒店</span>
						</a>
					</li>
					<li style="border-top:none;" @mouseenter="slideup(3)">
						<a href="">
							<img src="../assets/i4.png">
							<span class="ispan">游戏</span>
						</a>
					</li>
					<li style="border-left:none;">
						<a href="">
							<img src="../assets/i5.png">
							<span>企业购</span>
						</a>
					</li>
					<li>
						<a href="">
							<img src="../assets/i6.png">
							<span>加油卡</span>
						</a>
					</li>
					<li>
						<a href="">
							<img src="../assets/i7.png">
							<span>电影票</span>
						</a>
					</li>
					<li>
						<a href="">
							<img src="../assets/i8.png">
							<span>火车票</span>
						</a>
					</li>
					<li style="border-left:none;">
						<a href="">
							<img src="../assets/i9.png">
							<span>众筹</span>
						</a>
					</li>
					<li>
						<a href="">
							<img src="../assets/i10.png">
							<span>理财</span>
						</a>
					</li>
					<li>
						<a href="">
							<img src="../assets/i11.png">
							<span>礼品卡</span>
						</a>
					</li>
					<li>
						<a href="">
							<img src="../assets/i12.png">
							<span>白条</span>
						</a>
					</li>

				</ul>
			</div>
			<div class="ihide" id="ihide"> 
				<i class="el-icon-circle-close" @click="slidedown"></i>
				<div class="ihideItem" style="display:block;" id="ihitem1">
					<ul>
						<li @mouseenter="slideright(1,0)"><a href="" style="color:#fff;background:red;">话费充值</a></li>
						<li @mouseenter="slideright(1,1)"><a href="">流量充值</a></li>
						<li @mouseenter="slideright(1,2)"><a href="">套餐变更</a></li>
					</ul>
					<div class="Dcontainer" id="Dcontainer">
						<div class="">
							<span>号码</span>
							<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
							<br>
							<span>面值</span>
							<select style="margin-top:8px;width:53px;">
								<option value="10">10元</option>
								<option value="20">20元</option>
								<option value="30">30元</option>
								<option value="50">50元</option>
								<option value="100">100元</option>
								<option value="200">200元</option>
								<option value="300">300元</option>
							</select>
							<span style="color:red;">￥98.0-￥100.0</span>
							<br>
							<input type="submit" name="" value="快速充值" class="ibutton">
							<br>
							<span >
								<a href="" style="color:#527cdb !important;">
									<i class="el-icon-star-on"></i>
									<span>抢50元话费券</span>
								</a>
				
							</span>
						</div>
					<div>
						<span>号码</span>
						<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
						<br>
						<span>流量</span>
						<select style="margin-top:8px;width:53px;">
							<option value="1">全国</option>
							<option value="2">省内</option>
						</select>
						<select style="margin-top:8px;width:53px;">
							<option value="1">50M</option>
							<option value="2">100M</option>
							<option value="3">200M</option>
							<option value="4">300M</option>
							<option value="5">500M</option>
						</select>
						<br>
						<span style="color:red;">￥7.5-￥10.0</span>
						<br>
						<input type="submit" name="" value="快速充值" class="ibutton">
						<br>
						<span >
							<a href="" style="color:#527cdb !important;">
							<i class="el-icon-star-on"></i>
							<span>抢50元话费券</span>
						</a>
			
						</span>
					</div>
					<div>
						<span>号码</span>
						<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
						<br>
						<span>月费</span>
						<select style="margin-top:8px;width:60px;">
							<option value="1">138元</option>
							<option value="2">100元</option>
							<option value="3">200元</option>
							<option value="4">300元</option>
							<option value="5">500元</option>
						</select>
						<span style="color:red;">5元1G流量</span>
						<br>
						<input type="submit" name="" value="便利变更" class="ibutton">
						<br>
						<span >
							<a href="" style="color:#527cdb !important;">
							<i class="el-icon-star-on"></i>
							<span>抢50元话费券</span>
						</a>
			
						</span>
					</div>
				    </div>
			
				</div>
				<div class="ihideItem" id="ihitem2" >
					<ul>
						<li @mouseenter="slideright(2,0)"><a href="" style="color:#fff;background:red;">国内机票</a></li>
						<li @mouseenter="slideright(2,1)"><a href="">国际/港澳台</a></li>
						<li @mouseenter="slideright(2,2)"><a href="">特惠活动</a></li>
					</ul>
					<div class="Dcontainer" id="Dcontainer">
						<div class="">
							<span>号码</span>
							<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
							<br>
							<span>面值</span>
							<select style="margin-top:8px;width:53px;">
								<option value="10">10元</option>
								<option value="20">20元</option>
								<option value="30">30元</option>
								<option value="50">50元</option>
								<option value="100">100元</option>
								<option value="200">200元</option>
								<option value="300">300元</option>
							</select>
							<span style="color:red;">￥98.0-￥100.0</span>
							<br>
							<input type="submit" name="" value="快速充值" class="ibutton">
							<br>
							<span >
								<a href="" style="color:#527cdb !important;">
									<i class="el-icon-star-on"></i>
									<span>抢50元话费券</span>
								</a>
				
							</span>
						</div>
					<div>
						<span>号码</span>
						<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
						<br>
						<span>流量</span>
						<select style="margin-top:8px;width:53px;">
							<option value="1">全国</option>
							<option value="2">省内</option>
						</select>
						<select style="margin-top:8px;width:53px;">
							<option value="1">50M</option>
							<option value="2">100M</option>
							<option value="3">200M</option>
							<option value="4">300M</option>
							<option value="5">500M</option>
						</select>
						<br>
						<span style="color:red;">￥7.5-￥10.0</span>
						<br>
						<input type="submit" name="" value="快速充值" class="ibutton">
						<br>
						<span >
							<a href="" style="color:#527cdb !important;">
							<i class="el-icon-star-on"></i>
							<span>抢50元话费券</span>
						</a>
			
						</span>
					</div>
					<div>
						<img src="../assets/pic1.png">
					</div>
				    </div>
				</div>
				<div class="ihideItem" id="ihitem3">
					<ul>
						<li @mouseenter="slideright(3,0)"><a href="" style="color:#fff;background:red;">国际/港澳台</a></li>
						<li @mouseenter="slideright(3,1)"><a href="">促销活动</a></li>
					</ul>
					<div class="Dcontainer" id="Dcontainer">
						<div class="">
							<span>号码</span>
							<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
							<br>
							<span>面值</span>
							<select style="margin-top:8px;width:53px;">
								<option value="10">10元</option>
								<option value="20">20元</option>
								<option value="30">30元</option>
								<option value="50">50元</option>
								<option value="100">100元</option>
								<option value="200">200元</option>
								<option value="300">300元</option>
							</select>
							<span style="color:red;">￥98.0-￥100.0</span>
							<br>
							<input type="submit" name="" value="快速充值" class="ibutton">
							<br>
							<span >
								<a href="" style="color:#527cdb !important;">
									<i class="el-icon-star-on"></i>
									<span>抢50元话费券</span>
								</a>
				
							</span>
						</div>
					<div>
						<span>号码</span>
						<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
						<br>
						<span>流量</span>
						<select style="margin-top:8px;width:53px;">
							<option value="1">全国</option>
							<option value="2">省内</option>
						</select>
						<select style="margin-top:8px;width:53px;">
							<option value="1">50M</option>
							<option value="2">100M</option>
							<option value="3">200M</option>
							<option value="4">300M</option>
							<option value="5">500M</option>
						</select>
						<br>
						<span style="color:red;">￥7.5-￥10.0</span>
						<br>
						<input type="submit" name="" value="快速充值" class="ibutton">
						<br>
						<span >
							<a href="" style="color:#527cdb !important;">
							<i class="el-icon-star-on"></i>
							<span>抢50元话费券</span>
						</a>
			
						</span>
					</div>
				    </div>
				</div>
				<div class="ihideItem" id="ihitem4">
					<ul>
						<li @mouseenter="slideright(4,0)"><a href="" style="color:#fff;background:red;">点卡</a></li>
						<li @mouseenter="slideright(4,1)"><a href="">QQ</a></li>
						<li @mouseenter="slideright(4,2)"><a href="">页游</a></li>
					</ul>
					<div class="Dcontainer" id="Dcontainer">
						<div class="">
							<span>号码</span>
							<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
							<br>
							<span>面值</span>
							<select style="margin-top:8px;width:53px;">
								<option value="10">10元</option>
								<option value="20">20元</option>
								<option value="30">30元</option>
								<option value="50">50元</option>
								<option value="100">100元</option>
								<option value="200">200元</option>
								<option value="300">300元</option>
							</select>
							<span style="color:red;">￥98.0-￥100.0</span>
							<br>
							<input type="submit" name="" value="快速充值" class="ibutton">
							<br>
							<span >
								<a href="" style="color:#527cdb !important;">
									<i class="el-icon-star-on"></i>
									<span>抢50元话费券</span>
								</a>
				
							</span>
						</div>
					<div>
						<span>号码</span>
						<input type="text" name="" value="移动/联通/电信"  onfocus="this.value=''">
						<br>
						<span>流量</span>
						<select style="margin-top:8px;width:53px;">
							<option value="1">全国</option>
							<option value="2">省内</option>
						</select>
						<select style="margin-top:8px;width:53px;">
							<option value="1">50M</option>
							<option value="2">100M</option>
							<option value="3">200M</option>
							<option value="4">300M</option>
							<option value="5">500M</option>
						</select>
						<br>
						<span style="color:red;">￥7.5-￥10.0</span>
						<br>
						<input type="submit" name="" value="快速充值" class="ibutton">
						<br>
						<span >
							<a href="" style="color:#527cdb !important;">
							<i class="el-icon-star-on"></i>
							<span>抢50元话费券</span>
						</a>
			
						</span>
					</div>
					<div>
						<img src="../assets/pic1.png">
					</div>
				    </div>
				</div>
			</div>
		</div>
	</div>
</template>
<script type="text/javascript">
	export default{
		data(){
			return{
				user:'',
				activename:'first'
			}
		},
		mounted:function(){
			var li = document.getElementById("tab").getElementsByTagName("li");
			var tab1 = document.getElementById("tab1");
			var tab2 = document.getElementById("tab2");
			var srco=document.getElementById("roll");
			li[1].onmouseover = function(){
				srco.style.transform="translateX(52px)";
				tab1.style.display="none";
				tab2.style.display="block";
			}
			li[0].onmouseover = function(){
				srco.style.transform="translateX(0px)";
				tab2.style.display="none";
				tab1.style.display="block";
			}
		},
		methods:{
			slideup:function(index){
				var ishow = document.getElementById("ishow");
				var ispan = ishow.getElementsByClassName("ispan");
				var ihide = document.getElementById("ihide");
				var ihideItem = document.getElementsByClassName("ihideItem");
				ishow.style.transform="translateY(-40px)";
				ihide.style.transform="translateY(-185px)";
				for(var i=0;i<4;i++){
					if(i==index){
						ihideItem[i].style.display="block";
						ispan[i].style.borderTop = "2px solid red";
					}
					else{
						ihideItem[i].style.display="none";
						ispan[i].style.borderTop = "2px solid #fff";
						
					}
				}
			},
			slidedown:function(){
				var ishow = document.getElementById("ishow");
				var ihide = document.getElementById("ihide");
				var ispan = ishow.getElementsByClassName("ispan");
				ishow.style.transform="translateY(0px)";
				ihide.style.transform="translateY(0px)";
				for(var i=0;i<4;i++){
					ispan[i].style.borderTop = "2px solid #fff";
				}
			},
			slideright:function(index1,index2){
				var id = "ihitem"+index1;
				var ihitem = document.getElementById(id);
				var A = ihitem.getElementsByTagName("a");
				var Dcontainer = ihitem.getElementsByClassName("Dcontainer");
				for(var i=0;i<4;i++){
					if(i==index2){
						A[i].style.color = "#fff";
						A[i].style.background="red";
					}
					else{
						A[i].style.color = "#666";
						A[i].style.background="#fff";
					}
				}
				switch(index2){
					case 0:
					Dcontainer[0].style.transform="translateX(0px)";
					break;
					case 1:
					Dcontainer[0].style.transform="translateX(-190px)";
					break;
					case 2:
					Dcontainer[0].style.transform="translateX(-380px)";
					break;
				}
			}
		}
	}
</script>
<style type="text/css">
	.rightMain{
		float:left;
		width:190px;
		height:100%;
		margin-left: 10px;
		background: #fff;
		overflow:hidden; 
		text-align: left;
		font-size: 12px;
	}
	.rightMain a{
		color:#666;
	}
	.Rtop{
		width:160px;
		height:115px;
		border-bottom: 1px solid #ccc;
		padding:0 15px;
		font-size: 12px;
	}
	.amsg{
		color:#666;
	}
	.rightMain a{
		text-decoration: none;
	}
	.amsg:hover{
		color:red;
	}
	.Rmid{
		width:100%;
		height:154px;
		border-bottom: 1px solid #ccc;
	}
	.Rbot{
		width: 100%;
		height:210px;
		position:relative;
		overflow: hidden;
	}
	.headPortrait{
		float:left;
		margin-right: 10px;
	}
	.headPortrait img{
		width:50px;
		height:50px;
		border-radius:50px;
	}
	.abutton{
		border:2px solid red;
		padding: 3px 10px;
		height:30px;
		color:red;
	}
	.abutton:hover{
		background: red;
		color:#fff;
	}
	.tab ul {
		width:90%;
		margin:0 auto;
		border-bottom:1px solid #ccc;
		height:30px;
		list-style: none;
		font-size: 12px;
	}
	.tab ul span{
		float:right;
		margin-top: 8px;
	}
	.tab ul li {
		float:left;
		width:48px;
		height:20px;
		text-align: center;
		margin-top: 8px;
	}
	.tab_roll{
		width:26px;
		position:absolute;
		top:31px;
		left:17px;
		border:1px solid red;
		transition:transform .5s;
	}
	.tabHover {
		width:90%;
		margin:15px auto;
	}
	.tabHover ul{
		list-style: none;
	}
	.tabHover ul li a{
		color:#666;
		line-height: 25px;
	}
	.tabHover ul li a:hover{
		color:red;
	}
	.ishow ul {
		list-style: none;
		transition: transform .3s;
	}
	.ishow ul li{
		width:45px;
		height:66px;
		float:left;
		border:1px solid #ccc;
		border-bottom: none;
		border-right: none;
		text-align: center;
	}
	.ishow{
		width:100%;
		height:100%;
	}
	.ishow ul li>a{
		width:40px;
		height:45px;
		display: inline-block;
		margin-top:5px;
		color:#666;
	}
	.ishow ul li>a:hover{
		color:red;
	}
	.ishow ul li>a img{
		width:90%;
		height:30px;
	}
	.ishow ul li>a span{
		display: inline-block;
		width:100%;
		padding-top:3px;
		margin-top: 2px;
		border:2px solid #fff;
	}
	.ihide{
		width:100%;
		height:186px;
		position: absolute;
		top:210px;
		transition: transform .3s;
		background: #fff;
	}
	.ihideItem{
		width:100%;
		height:150px;
		display: none;
		margin-top: 28px;
	}
	.ihideItem ul{
		width:100%;
		height:30px;
		list-style: none;
		text-align: center;
		padding-left: 7px;
		margin-top: -5px;
	}
	.ihideItem ul li{
		float:left;
		margin:0px 5px;
	}
	.Dcontainer{
		width:300%;
		transition: transform .5s;
	}
	.Dcontainer div{
		width:175px;
		padding-left: 15px;
		float:left !important;
	}
	.ihideItem span{
		margin-right:3px;
	}
	.ihideItem input{
		width:83px;
		font-size: 12px;
		color:#666;		
	}
	.ihideItem img{
		display: inline-block;

	}
	.ibutton{
		margin-top:8px;
		background: red;
		color:#fff !important;
		border:none;
		height:25px !important;
		margin-bottom: 5px;
	}
</style>