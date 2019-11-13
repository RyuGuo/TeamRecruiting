<template>
	<div style="height:100%">
		<PageHeader :isshowlogo="false"  title="团队导师"></PageHeader>
			<!-- <p class="text-title">团队导师</p> -->
			<p class="info text">{{contentList[0]}}</p>
<!-- 			<TextContent 
				:contentList="contentList"
			></TextContent> -->
			<swiper 
				class="swiper" 
				:indicator-dots="true" 
				:autoplay="true" 
				:interval="5000" 
				:duration="2000" 
				current="0" 
				indicator-active-color="rgba(255,255,255,0.8)"
			>
				<block v-for="(teacher,index) in teacherList" :key="index">
					<swiper-item>
						<div class="card">
							<TeacherCard :teacher="teacher"></TeacherCard>
						</div>
						<!-- <image lazy-load="true" :src="teacher.imgurl"></image> -->
					</swiper-item>
				</block>
			</swiper>
<!-- 			<scroll-view scroll-x class="teachers">
				
			</scroll-view> -->
<!-- 			<p class="little-tip">
				&lt;&lt; 右滑查看更多导师介绍 &gt;&gt;
			</p> -->
	</div>
</template>

<script>
	import PageHeader from "@/components/PageHeader.vue";
	import TeacherCard from "@/components/TeacherCard.vue";
	import TextContent from "@/components/TextContent.vue";
	export default {
		components: {
			PageHeader,
			TeacherCard,
			TextContent
		},
		data() {
			return {
				teacherList : [
					{
						name: '刘玉',
						desc: '电子信息与通信学教授, 硕士研究生导师,原启明学院副院长,Dian团队创始人兼董事长,创业红娘',
						research: '移动互联网技术、多媒体通信技术',
						imgurl: './static/image/teachers/teachers_02.png',
					},
					{
						name: '黄晓庆',
						desc: '电子信息与通信学院院长,达闼科技创始人兼CEO,前中国移动研究院院长,"千人计划"国家特聘专家,Dian团队名誉CEO',
						research: '无线通信,云端智能机器人',
						imgurl: './static/image/teachers/teachers_01.png',
					},
					{
						name: '钟国辉',
						desc: '电子信息与通信学院副教授,硕士研究生导师,系统分析,Dian团队执行CEO兼软件CTO',
						research: '嵌入式系统、网络安全',
						imgurl: './static/image/teachers/teachers_03.png',
					},
					{
						name: '刘勃',
						desc: '电子信息与通信学院副教授,硕士研究生导师,Dian团队CFO',
						research: '数字信号处理,智能仪器、光通信,多媒体技术',
						imgurl: './static/image/teachers/teachers_04.png',
					},
					{
						name: '颜庆华',
						desc: '华中科技大学电信系硕士，武汉悦然心动网络科技有限公司CEO，Dian团队COO',
						research: '移动互联网',
						imgurl: './static/image/teachers/teachers_05.png',
					},
					{
						name: '刘合群',
						desc: '北京天文馆副研究员,宇宙力网理论开创者,人体物理医学奠基人',
						research: '无创针术,医学学科交叉研究',
						imgurl: './static/image/teachers/teachers_06.png',
					},
					{
						name: '王兴刚',
						desc: '电子信息与通信学院副教授,华中科技大学电信系博士,Dian团队人工智能CTO',
						research: '计算机视觉,深度学习,物体识别和检测,弱监督学习等',
						imgurl: './static/image/teachers/teachers_07.png',
					},
					{
						name: '曹洋',
						desc: '电子信息与通信学院副教授,华中科技大学电信系博士,Dian团队研究生主管',
						research: '视频分发与处理,人工智能,5G通信,物联网',
						imgurl: './static/image/teachers/teachers_08.png',
					},
					{
						name: '周潘',
						desc: '电子信息与通信学院副教授,美国佐治亚理工学院博士,研发工程师',
						research: '大数据分析、数据与网络安全与隐私、认知无线电网络与无线调度算法等',
						imgurl: './static/image/teachers/teachers_09.png',
					},
					{
						name: '黑晓军',
						desc: '电子信息与通信学院副教授,香港科技大学电子与计算机工程系博士',
						research: '移动边缘计算,软件定义网络和嵌入式网络系统',
						imgurl: './static/image/teachers/teachers_10.png',
					},
					{
						name: '张成伟',
						desc: '电子信息与通信学院讲师,华中科技大学信息与通信工程博士',
						research: '网络测量、网络性能评估和互联应用',
						imgurl: './static/image/teachers/teachers_11.png',
					},
					{
						name: '高雅玙',
						desc: '电子信息与通信学院讲师,香港城市大学电子工程博士,助理教授',
						research: '无线通信,网络优化,随机接入网络',
						imgurl: './static/image/teachers/teachers_12.png',
					},
					{
						name: '钱彦旻',
						desc: '上海交通大学计算机科学与工程系副教授,清华大学博士,剑桥大学博士后,思必驰-上海交大联合实验室副主任,Kaldi创始人之一',
						research: '语音和语言处理,人机交互,模式识别,机器学习等',
						imgurl: './static/image/teachers/teachers_13.png',
					}
				],
				contentList: [
					'Dian 团队的全称是“基于导师制的人才孵化站”，诸位导师会在项目过程中给予项目组成员全方位的指导。'
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
@import "@/style/text.scss";
@import "@/style/common.scss";
.text {
	margin-top: 20px;
}
.swiper{
	height: 62%;
	margin-top: 44px;
}
.card {
	display: flex;
	justify-content: center;
	width: 100%;
}
.little-tip {
	color: $darkgray;
	font-size: 10px;
	text-align: center;
}
.info {
	font-size: 16px;
	font-weight: 700px;
	padding: 0 30px;
	margin-bottom: 20px;
}
</style>
