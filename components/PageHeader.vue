<template>
	<div style="height: 50px;">
		<div class="header">
			<div class="logo" v-if="isshowlogo==1">
				<img :src="logoUrl" mode="" ></img>
			</div>
<!-- 			<div v-else class="logo-no"></div> -->
			<div class="header-title" v-else>
				{{title}}
			</div>
<!-- 			<ul class="navbar">
				<view class="navbutton" @click="pageJump('http://35.229.249.48/')">报名</view>
				<view class="navbutton" @click="pageJump('http://35.229.249.48/query/')">进度</view>
			</ul> -->
<!-- 			<div class="navButton" @click="handleClick">
				<image src="/static/image/hamberger.png" mode=""></image>
			</div> -->
		</div>
		
<!-- 		<ul id="nav" class="navlist animated" :class="[isshow?'slideInRight':'slideOutRight',{hidden:isHidden}]">
			<li @click="pageJump(0)">团队简介</li>
			<a href="http://35.229.249.48/"><li>报名填写</li></a>
			<a href="http://35.229.249.48/query/"><li>进度查询</li></a>
		</ul> -->
	</div>
</template>

<script>
export default {
	props: {
		isshowlogo: Boolean,
		title: String,
	},
	data() {
		return {
			logoUrl: './static/image/site-logo.png',
			isshow: false,
			isHidden: true,
		};
	},
	methods:{
		handleClick() {
			this.isHidden = false;
			this.isshow = !this.isshow
			if(this.isshow==true) {
				let d = 0;
				this.timer = setInterval(()=>{
					d += 1;
					if(d>=5){
						this.isshow = false;
						clearInterval(this.timer);
					}
				},1000);
			} else {
				clearInterval(this.timer);
			}
		},
		pageJump(url) {
			window.location.href = url;
		}
	}
}
</script>

<style lang="scss" scoped>
@import "../style/Animate.scss";
a {
	text-decoration: none;
	color: $white;
}
.header {
	display: flex;
	height: 50px;
	// padding: 0 20px;
	align-items: center;
	justify-content: space-around;
	// font-size: 0;
	&-title {
		text-align: center;
		color: $bluegrayalittlelight;
		font-size: 20px;
		font-weight: bold;
	}
}

.logo {
	width:100%;
	padding: 0 5px;
	img {
		width: 90px;
		height: 40px;
	}
	&-no {
		width: 24px;
		height: 30px;
	}
}

// .navButton {
// 	height: 24px;
// 	width: 30px;
// 	text-align: center;
// 	image {
// 		height: 24px;
// 		width: 24px;
// 	}
// }
// 
// .navButton:active{
// 	background: rgba(0,0,0,0.3);
// }
		
// .navlist {
// 	position:relative;
// 	left: 72%;
//     top: 0;
// 	z-index: 9999;
// 	box-shadow: 3px 4px 6px rgba(0,0,0,0.3);
// 	li {
// 		height: 34px;
// 		width: 100px;
// 		text-align: center;
// 		list-style: none;
// 		color: $white;
// 		border: 1px $orange solid;
// 		font-size: 14px;
// 		line-height: 34px;
// 		//background: $purple;
// 		// background: linear-gradient(0deg,$blue , $bluenormal 50% ,$blue 100%);
// 		background: rgba(0,0,0,0.6);
// 	}
// 	// li:hover {
// 	// 	color: $black;
// 	// 	background: rgba(255,255,255,0.6);
// 	// }
// 	li:active {
// 		color: $black;
// 		background: rgba(255,255,255,0.6);
// 	}
// }

.navbutton {
	display: inline-block;
	width: 70px;
	height: 30px;
	border: 1px $orange solid ;
	border-radius: 15px;
	text-align: center;
	line-height: 30px;
	margin: 0 4px;
	font-size: 16px;
	background: rgba(255,255,255,0.6);
}

.navbutton:active {
	color: $gray;
	background: rgba(180,180,180,0.7);
}

.hidden {
	display: none;
}
</style>
