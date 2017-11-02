<template>
	<div>
		<div class="TopImg">
			<transition name="fade">
			<el-row style="background-color: #ff99b6" class="topnav" v-if="show">
				<el-col :span="24">
					<div class="test">
						<img src="../assets/topnav.jpg">
						<i class="el-icon-circle-close" @click="show=false"></i>
					</div>
				</el-col>
			</el-row>
			</transition>
		</div>
		<div class="short-nav">
			<shortNav></shortnav>
		</div>
		<div>
			<headNav></headNav>
		</div>
			<mainContent></mainContent>
			<secondContent></secondContent>
			<fixRight></fixRight>
	</div>
</template>
<script>
import shortNav from './shortnav';
import headNav from './headnav';
import mainContent from './mainContent';
import secondContent from './secondContent';
import fixRight from './fixRight';
export default {
	components:{
		shortNav,
		headNav,
		mainContent,
		secondContent,
		fixRight
	},
  data () {
    return {
      show:true
    }
  }
}
</script>
<style type="text/css">
	.fade-enter-active, .fade-leave-active {
  		transition: opacity .5s
		}
	.fade-enter, .fade-leave-to /* .fade-leave-active in below version 2.1.8 */ {
  		opacity: 0
		}
	.test{
		width:1190px;
		height:80px;
		margin:0 auto;
		position:relative;
	}
	.el-icon-circle-close{
		position:absolute;
		top:10px;
		right:20px;
	}
</style>