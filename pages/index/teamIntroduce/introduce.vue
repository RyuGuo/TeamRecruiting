<template>
	<div>
		<PageHeader :isshowlogo="false" title="项目组介绍"></PageHeader>
		<swiper class="swiper" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="2000" current="0" indicator-active-color="rgba(255,255,255,0.8)">
			<block v-for="item in teamInfo" :key="item.name">
				<swiper-item>
					<div class="card">
						<TeamCard :name="item.name" 
							:imgUrl="item.imgUrl" 
							:info="item.info"
							:tech="item.tech"
						></TeamCard>
					</div>
				</swiper-item>
			</block>
		</swiper>
	</div>
</template>

<script>
import PageHeader from "@/components/PageHeader.vue"
import TeamCard from "@/components/TeamCard.vue"
	export default {
		components:{
			PageHeader,
			TeamCard,
		},
		data() {
			return {
				teamInfo: [
					{
						name:"AI组",
						imgUrl: '/static/AI.png',
						info: 'AI组是Dian团队人数最多的项目组，致力于研究和开发更加深刻而有用的人工智能，主要研究方向有计算机视觉、自然语言处理、生成式对抗网络以及深度强化学习。其中的每个方向都是十分有趣又在当下十分火热的，相信我们能脚踏实地，共创辉煌！',
						tech: 'Natural Language Processing、Machine Learning、Deep Learning、Reinforcement Learning'
					},{
						name:"Intel组",
						imgUrl: '/static/Intel.png',
						info: '本项目为华中科技大学Dian团队与英特尔亚太研发有限公司合作的软件开发项目。项目目标为对当前3GPP（第三代合作伙伴计划）组织正在制定的5G NR协议数据平面做软件实现和性能优化。5G网络是当前最热门的研究方向之一，Intel公司在此方面有着全面的商业布局和深厚的技术积累。同时，公司对参与合作项目的Dian团队成员也提供了从硬件到软件的全方位支持，项目组成员每周都有机会与Intel公司项目经理进行技术交流。',
						tech: '5G、C、Linux'
					},{
						name:"迅测组",
						imgUrl: '/static/IoT.png',
						info: '迅测组依托Dian团队老队员的创业公司，该项目致力于打造绿色出行新方式，项目组秉承以老带新的优良传统。在这里，你不再是一个人在战斗。我们有一批经过多年职场历练的优秀毕业老队员亲身指导，也有众多优秀的学长学姐们传授经验。从硬件到嵌入式、从后台到前端，你可以在自己喜欢的方向大展身手，体验整个项目流程的开发。在这里，你将收获知识、技术、友谊和成长。',
						tech: 'C、Node.js、Android、iOS、Weex'
					},{
						name:"启亦电子组",
						imgUrl: '/static/qiyi.png',
						info: '启亦电子组与上海启亦电子科技有限公司合作进行项目开发。项目致力于实现电力测量设备与应用软件的交互，打造电子电力APP。目前项目组主要着力点为通过移动开发实现硬件显示，项目涉及到Android开发、IOS开发、嵌入式开发、Windows软件开发。无论你擅长哪方面，都可以在项目组中大展身手。',
						tech: 'SoC软硬件协同设计、Android开发、Windows桌面程序开发'
					},{
						name:"鹰眼组",
						imgUrl: '/static/web.png',
						info: '鹰眼组目标是开发一款智能监考考试系统，结合机器学习的方法，全方位智能监考，让作弊者无计可施。主要应用场合是企业的招聘考试，职业评级考试等。我们主要负责该系统web端的开发，在这里你可以接触到当前流行的前端/后台开发框架，了解AI技术如何应用到监考领域等。',
						tech: 'Python，Java，React，Vue，微信小程序等'
					},{
						name: '网安组',
						imgUrl: '/static/wangguan.png',
						info: '网络安全是Dian团队一大技术方向。我们依托于Dian团队的导师资源，凭借团队在网络方向深厚积累，与中科院信工所等国家资深网络安全机构深入合作，将机器学习等最新技术引入到网络流量分析，安全威胁特征识别等网络安全前沿研究方向。培养网络安全方面的人才，并给出切实可行的防护解决方案。',
						tech: '渗透技术、加密技术、P2P技术、流量大数据分析技术',
					},{
						name:"深信服组",
						imgUrl: '/static/shenxinfu.png',
						info: '深信服组于2018年5月成立，这也是团队与深信服公司首次合作，本期项目目标是实现一个安全的邮件客户端。整体项目从UI、中间层和业务层以及底层协议全部需要自己实现。有项目经理入驻团队进行指导协助项目进行。UI使用现阶段流行的跨平台框架react-native进行开发，中间层根据平台使用oc和java进行开发，底层以及协议层使用C++11进行开发，也是团队为数不多的用C++开发的项目组。',
						tech: 'C++、OC、java、react-native'
					},{
						name:"悦然心动组",
						imgUrl: '/static/yueranxindong.png',
						info: '在悦然心动，你能够了解最新的项目需求、接触到真实的企业项目、可以和一线的工程师并肩作战。公司技术方向十分广泛，包括前端后台开发，iOS开发、Android开发，Unity游戏开发等。每个项目组成员都会有公司相关的专业人员带领学习，真正的投入到产品的设计研发中；在此过程中不仅可以学到技术，更能够见证自己参与研发的产品从初具雏形到最终发布的全过程。',
						tech: 'iOS/Android开发、Nodejs后台开发、Unity游戏开发等'
					},{
						name: '区块链组',
						imgUrl: '/static/qukuailian.png',
						info: '区块链项目组，欢迎热爱区块链技术，热爱钻研，热爱编程，爱动手实践，具有团队合作精神的你加入！',
						tech: '共识算法（DPOS+网络编码和路由）'
					}
				]
			}
		},
		methods:{
			
		}
	}
</script>

<style lang="scss">
.card {
	display: flex;
	justify-content: center;
	//width: 100%;
}
.swiper {
	margin-top: 15px;
	height: 540px;
}
</style>
