<template>
	<div>
		<PageHeader :isshowlogo="false"  title="团队历史"></PageHeader>
		<div class="text">
		<TextContent 
			:contentList="contentList"
		></TextContent>
		</div>
<!-- 		<div class="text">
			<p class="text-title">团队导师</p>
			<scroll-view scroll-x class="teachers">
				<image class="teachers" src="/static/image/teachers1.jpg"/>
				<image class="teachers" src="/static/image/teachers2.jpg"/>
				<image class="teachers" src="/static/image/teachers3.jpg"/>
				<image class="teachers" src="/static/image/teachers4.jpg"/>
			</scroll-view>
			<p class="little-tip">
				&lt;&lt; 右滑查看更多导师介绍 &gt;&gt;
			</p>
		</div> -->
	</div>
</template>

<script>
import PageHeader from "@/components/PageHeader.vue"
import TextContent from "@/components/TextContent.vue"
	
	export default {
		components: {
			PageHeader,
			TextContent,
		},
		data() {
			return {
				contentList:[
					'2002年3月，Dian团队由刘玉教授创建,并成为首批入驻启明学院的学生团队。通过“干中学”的培养模式，辅以真实项目的切身实践，培养学生的创新能力、实践精神和综合素质，是团队的初衷。',
					'“历平凡事，成放心人”，是团队的口号。Dian团队经过17年的成长，在导师和历届队员的共同奋斗下，逐渐发展壮大，团队有28名顾问，均是各个行业的专家学者、领军人物。'
				]
			}
		},
		methods: {
			// handleClick() {
			// 	uni.reLaunch({
			// 		url: "/pages/index/introduce/introduce2"
			// 	})
			// }
		}
	}
</script>

<style lang="scss">
@import "@/style/text.scss";
@import "@/style/common.scss";
// .little-tip {
// 	color: $darkgray;
// 	font-size: 10px;
// 	text-align: center;
// }
// .teachers {
// 	width: 311px;
// 	height: 135px;
// 	margin: 10px auto;
// 	display: flex;
// 	white-space: nowrap;
// 	image {
// 		width: 311px;
// 		height: 135px;
// 		display: inline-block;
// 	}
// }
.text {
	margin-top: 20px;
}
</style>
