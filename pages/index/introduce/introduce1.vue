<template>
	<div>
		<PageHeader :isshowlogo="false"  title="团队简介"></PageHeader>
		<TextContent title="团队历史"
			maincontent="2002年3月，Dian团队由刘玉教授创建,并成为首批入驻启明学院的学生团队。通过真实的项目实践培养学生的创新能力、实践精神和综合素质，是团队的初衷。"
			addcontent="“历平凡事，成放心人”，是团队的口号。经过16年的成长，在导师和历届队员的共同奋斗下，名顾问组成，既有IT领域的知名学者，也有各行各业的著名企业家。"
		></TextContent>
		<div class="text">
			<p class="text-title">团队导师</p>
			<!-- <TextPicture :type="0"></TextPicture> -->
			<scroll-view scroll-x class="teachers">
				<image class="teachers" src="/static/teachers1.jpg"/>
				<image class="teachers" src="/static/teachers2.jpg"/>
				<image class="teachers" src="/static/teachers3.jpg"/>
				<image class="teachers" src="/static/teachers4.jpg"/>
			</scroll-view>
			<p class="little-tip">
				&lt;&lt; 右滑查看更多导师介绍 &gt;&gt;
			</p>
		</div>
	</div>
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
					url: "/pages/index/introduce/introduce2"
				})
			}
		}
	}
</script>

<style lang="scss">
@import "@/style/text.scss";
@import "@/style/common.scss";
.little-tip {
	color: $darkgray;
	font-size: 10px;
	text-align: center;
}
.teachers {
	width: 311px;
	height: 135px;
	margin: 10px auto;
	display: flex;
	white-space: nowrap;
	image {
		width: 311px;
		height: 135px;
		display: inline-block;
	}
}
.text {
	margin-top: 20px;
}
</style>
