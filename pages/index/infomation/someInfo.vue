<template>
	<div>
		<PageHeader :isshowlogo="false" title="招新相关"></PageHeader>
		<ul class="info-wrap">
			<li v-for="info_item in info" :key="info_item.title">
				<span class="info-title">{{info_item.title}}</span>
				<span class="info-content">{{info_item.content}}</span>
			</li>
		</ul>
		<div class="scan2D">
			<!-- 现在还没有二维码呢(；′⌒`) -->
			<image src="/static/1.jpg" />
			<p>长按识别二维码加入招新QQ群</p>
			<p>群号：{{QQ}}</p>
			<div class="copy" @click="copy">
				<image src="/static/copy.png" mode=""></image>
			</div>
		</div>
		<div class="longButton"><p>现在报名</p></div>
	</div>
</template>

<script>
import PageHeader from "../../../components/PageHeader.vue"
export default {
	components: {
		PageHeader,
	},
	data() {
		return {
			// 资料都需要改哦┌(.Д.)┐
			QQ: '**********',
			info: [
				{"title":"路演时间","content":"9月22日 7:00-18:00"},
				{"title":"路演地点","content":"韵苑路口"},
				{"title":"宣讲时间","content":"9月25日 19:30"},
				{"title":"宣讲地点","content":"东九楼B103"},
				{"title":"笔试时间","content":"9月27日"},
				{"title":"","content":""},
				{"title":"团队官网","content":"http://dian.org.cn"},
				{"title":"报名链接","content":"http://recruit.dian.org.cn"},
				{"title":"进度查询","content":"http://recruit.dian.org.cn/query"},
			]
		}
	},
	methods:{
		copy(){
		}
	}
}
</script>

<style lang="scss" scoped>
@import "@/style/common.scss";
.info {
	&-wrap {
		margin: 10px 27px 0 27px;
		list-style: none;
	}
	&-title {
		color: $white;
		font-size: 16px;
		font-weight: bold;
		margin-right: 10px;
	}
	&-content {
		color: $white;
		font-size: 16px;
	}
}
.scan2D {
	margin: 25px 0;
	text-align: center;
	image {
		width: 180px;
		height: 180px;
	}
	p {
		color: $white;
		text-align: center;
		font-size: 12px;
	}
	.copy {
		line-height: 0;
		position: absolute;
		left: 282px;
		top: 493px;
		image{
			width: 28px;
			height: 28px;
		}
	}
	.copy:active {
		background: rgba(0,0,0,0.3);
	}
}
.longButton {
	position: relative;
	left: 50%;
	transform: translate(-50%);
}
</style>
