<template>
	<view>
		<PageHeader :isshowlogo="false"  title="团队简介"></PageHeader>
		<TextContent title="团队现状"
			maincontent="到今天，团队已培养正式队员632名，孵化出54家企业。历届队员不乏学界栋梁，Google、微软、BAT等著名互联网企业任职者，独角兽企业CEO等等，其中，老队员张良伦、金亦冶、柯尊尧、吴一明等荣登福布斯排行榜；而孵化出的五十多家企业里，估值过亿的达14家。"
			addcontent="2019年初，团队成功开拓网络安全新方向，结合导师在网络方向深耕多年的技术积累，携手中科院信工所等资深安全研究机构，树起了网络安全方向的大旗。"
		></TextContent>
		<div class="text">
			<p class="text-title">照片</p>
			<TextPicture :type="1" :imgList="['/static/pic1.jpg','/static/pic2.jpg','/static/pic3.jpg']"></TextPicture>
		</div>
	</view>
</template>

<script>
import PageHeader from "@/components/PageHeader.vue"
import TextContent from "@/components/TextContent.vue"
import TextPicture from "@/components/TextPicture.vue"
	
	export default {
		components: {
			PageHeader,
			TextContent,
			TextPicture,
		},
		data() {
			return {
				
			}
		},
		methods: {
			handleClick() {
				uni.reLaunch({
					url: "/pages/index/teamIntroduce/index"
				})
			}
		}
	}
</script>

<style lang="scss">
@import "@/style/text.scss";
.text {
	margin-top: 20px;
}
</style>
