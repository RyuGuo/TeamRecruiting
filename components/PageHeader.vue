<template>
	<div style="height: 50px;">
		<div class="header">
			<div class="logo" v-if="isshowlogo==1">
				<image src="/static/site-logo.gif" mode="" ></image>
			</div>
			<div v-else class="logo-no"></div>
			<div class="header-title">
				{{title}}
			</div>
			<div class="navButton" @click="handleClick">
				<image src="/static/hamberger.png" mode=""></image>
			</div>
		</div>
		<ul id="nav" class="navlist animated" :class="[isshow?'slideInRight':'slideOutRight',{hidden:isHidden}]">
			<li @click="pageJump(0)">团队简介</li>
			<li @click="pageJump(1)">报名填写</li>
			<li @click="pageJump(2)">进度查询</li>
		</ul>
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
			isshow: false,
			isHidden: true,
		};
	},
	methods:{
		handleClick() {
			this.isHidden = false;
			this.isshow = !this.isshow
			if(this.isshow==true) {
				setTimeout(()=>{
					this.isshow=false
				},3000)
			}
		},
		pageJump(i) {
			console.log("跳往"+i+"页")
			let url = ''
			this.isshow = false;
			switch(i)
			{
				case 0: url = "/pages/index/index"
				break
				case 1: url = ""
				break
				case 2: url = ""
				break
			}
			uni.reLaunch({
				url: url,
			})
		}
	}
}
</script>

<style lang="scss" scoped>
@import "../style/Animate.scss";
.header {
	display: flex;
	height: 50px;
	padding: 0 20px;
	align-items: center;
	justify-content: space-between;
	&-title {
		text-align: center;
		color: $bluegrayalittlelight;
		font-size: 20px;
		font-weight: bold;
	}
}

.logo {
	image {
		width: 73px;
		height: 30px;
	}
	&-no {
		width: 24px;
		height: 24px;
	}
}

.navButton {
	height: 24px;
	width: 24px;
	image {
		height: 24px;
		width: 24px;
	}
}
		
.navlist {
	position:relative;
	left: 72%;
    top: 0;
	z-index: 9999;
	box-shadow: 3px 4px 6px rgba(0,0,0,0.3);
	li {
		height: 34px;
		width: 100px;
		text-align: center;
		list-style: none;
		color: $white;
		border: 1px $orange solid;
		font-size: 14px;
		line-height: 34px;
		//background: $purple;
		// background: linear-gradient(0deg,$blue , $bluenormal 50% ,$blue 100%);
		background: rgba(0,0,0,0.6);
	}
	// li:hover {
	// 	color: $black;
	// 	background: rgba(255,255,255,0.6);
	// }
	li:active {
		color: $black;
		background: rgba(255,255,255,0.6);
	}
}

.hidden {
	display: none;
}
</style>
