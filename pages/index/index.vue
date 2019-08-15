<template>
	<div class="page bg">
		<swiper class="page" :indicator-dots="false" :autoplay="false" :vertical="true" @change="handleChange">
			<swiper-item>
				<div class="page">
					<PageHeader :isshowlogo="true"  title="" scroll-with-animation="true"></PageHeader>
					<div class="video-wrap">
						<!-- 2018年的秋招视频，不要直接上传哦┏ (゜ω゜)=☞ -->
						<video src="https://apd-e3f75056217092d39b5314bcf1a512d9.v.smtcdns.com/vhot2.qqvideo.tc.qq.com/AWHnsYm9WAJqQqeJ7mObhUf4UwtKIzr-iThPNXJQmPI0/uwMROfz2r5zIIaQXGdGnC2dfDmb_xYKxrIGz_bGUg2Lja6ru/w07010sb70w.mp4?sdtfrom=v1010&guid=99be7923d9c51ad1ca45ee726cb03f36&vkey=E3CE2AA7F160AEAFFF24EB03E2EF6A79223AA09DA07AA6D4001945FDD53E7F1DB1315139B8C072D92FE4F9A5438DECC374AF73355C124CBF3025C6817BA0CFE6E9196148FB6657FB89335B1AB6F8538C540FB6AD56ACE93F2C885F11C7571638A119159A5201D4896A7B037DFFA8C1C3870F4DF724A3770213CF720673ECF867" controls></video>
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
					<teamIndex :isReady="current==3"></teamIndex>
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
import teamIndex from "./teamIntroduce/teamIndex.vue"
import introduce from "./teamIntroduce/introduce.vue"
import someInfo from "./infomation/someInfo.vue"

export default {
	components: {
		PageHeader,
		DropUpArrow,
		introduce1,
		introduce2,
		teamIndex,
		introduce,
		someInfo,
	},
	data() {
		return {
			current: 0
		}
	},
	onLoad() {

	},
	methods: {
		handleChange(mp) {
			if(mp.detail.source=="touch"){
				this.current = mp.detail.current;
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
	width: 100%;
}
.bg {
	background-image: url("/static/bg.JPG");
	background-repeat:no-repeat; 
	background-size:100% 100%;
	-moz-background-size:100% 100%;
}
.swiper {
	height: 100%;
}
.content {
	text-align: center;
	color: $white;
	font-size: 16px;
	margin-top: 84px;
}
.video-wrap {
	display: flex;
	justify-content: center;
	margin-top: 30px;
	video {
		width: 306px;
		height: 162px;
	}
}
</style>
