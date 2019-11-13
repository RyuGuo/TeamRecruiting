<template>
	<div class="page bg">
		<swiper class="page" :indicator-dots="false" :current="current" :autoplay="false" :vertical="true" @change="handleChange">
			<swiper-item>
				<div class="page">
					<PageHeader :isshowlogo="true"  title="" scroll-with-animation="true"></PageHeader>
					<div class="video-wrap">
						<!-- 2018年的秋招视频，不要直接上传哦┏ (゜ω゜)=☞ -->
						<video src="/static/video/publicity.mp4" controls></video>
					</div>
					<div class="content">
						<div class="animated fadeInUp" style="animation-delay: 0s;">
							<p>这是一个崭新的开始</p>
							<p>这是一个起飞的舞台</p>
							</br>
						</div>
						<div class="animated fadeInUp" style="animation-delay: 1s;">
							<p>在项目实践的磨练下</p>
							<p>我们可以点石成金，点亮未来</p>
							</br>
						</div>
						<div class="animated fadeInUp" style="animation-delay: 2s;">
							<p>Dian团队秋招大戏即将开拍</p>
							<p>各位Huster们确定不上拉了解一下吗？</p>
						</div>
					</div>
					<div class="drop">
						<DropUpArrow></DropUpArrow>
					</div>
				</div>
			</swiper-item>
			<swiper-item>
				<div class="page">
					<introduce1></introduce1>
				</div>
			</swiper-item>
			<swiper-item>
				<div class="page">
					<introduce2></introduce2>
				</div>
			</swiper-item>
			<swiper-item>
				<div class="page">
					<teachers></teachers>
				</div>
			</swiper-item>
			<swiper-item>
				<div class="page">
					<teamIndex :isReady="current==4"></teamIndex>
				</div>
			</swiper-item>
			<swiper-item>
				<div class="page">
					<introduce></introduce>
				</div>
			</swiper-item>
			<swiper-item>
				<div class="page">
					<someInfo></someInfo>
				</div>
			</swiper-item>
		</swiper>
	</div>
</template>

<script>
import PageHeader from "@/components/PageHeader.vue"
import DropUpArrow from "@/components/DropUpArrow.vue"
import introduce1 from "./introduce/introduce1.vue"
import introduce2 from "./introduce/introduce2.vue"
import teachers from "./introduce/teachers.vue"
import teamIndex from "./teamIntroduce/teamIndex.vue"
import introduce from "./teamIntroduce/introduce.vue"
import someInfo from "./infomation/someInfo.vue"

export default {
	components: {
		PageHeader,
		DropUpArrow,
		introduce1,
		introduce2,
		teachers,
		teamIndex,
		introduce,
		someInfo,
	},
	data() {
		return {
			current: 0,
			// videoUrl: './static/vedio/publicity.mp4'
		}
	},
	onLoad() {
		if (window.addEventListener)//FF,火狐浏览器会识别该方法
			window.addEventListener('DOMMouseScroll', this.wheel, false);
		window.onmousewheel  = this.wheel;
	},
	methods: {
		handleChange(mp) {
			if(mp.detail.source=="touch"){
				this.current = mp.detail.current;
			}
		},
		wheel(e){
			if(e.deltaY>0 && this.current<7-1){
				this.current++;
			} else if(e.deltaY < 0 && this.current>0){
				this.current --;
			}
		}
	}
}
</script>

<style lang='scss'>
@import "@/style/common.scss";
@import "@/style/Animate.scss";
.page {
	height: 100%;
	width: 375px;
	margin: auto;
}
/* .bg {
	background-image: url("/static/image/bg.jpg");
	background-repeat:no-repeat; 
	background-size:100% 100%;
	-moz-background-size:100% 100%;
} */
.swiper {
	height: 100%;
}
.content {
	text-align: center;
	color: $bluegray;
	font-size: 16px;
	/*margin-top: 30%;*/
	/*margin-top: 12%;*/
    position: absolute;
    width: 100%;
    top: 56%;
}
.video-wrap {
	display: flex;
	justify-content: center;
	margin-top: 25px;
	video {
		width: 306px;
		height: 162px;
	}
}
.drop{
	display: flex;
	position: absolute;
	bottom: 0px;
	left: 50%;
	transform: translate(-50%,-50%);
	justify-content: center;
}
</style>
