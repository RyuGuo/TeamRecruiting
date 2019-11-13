<template>
	<div class="text">
		<p class="text-title" v-if="title">{{title}}</p>
		<div class="text-content">
			<p v-for="(content,index) in contentList" :key="index">{{content}}</p>
<!-- 			<p>{{maincontent}}</p> -->
<!-- 			<div class="text-add-button" @click="handleShowAdd" v-if="isshowadd==false">read more</div> -->
			<!-- <p v-if="isshowadd==true" class="animated fadeIn">{{addcontent}}</p> -->
<!-- 			<p>{{addcontent}}</p> -->
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			title: String,
			maincontent: String,
			addcontent: String,
			contentList: Array,
		},
		data() {
			return {
				//isshowadd: false,
			};
		},
		methods:{
			// handleShowAdd() {
			// 	this.isshowadd = true 
			// }
		}
	}
</script>

<style lang="scss" scoped>
@import "../style/text.scss";
@import "@/style/Animate.scss";
.text{
	&-content {
		width: 240px;
		padding: 20px 30px;
		margin: auto;
		background: rgba(255,255,255,0.85);
		border-radius: 10px;
		p {
			color: $bluegray;
			font-size: 16px;
			text-indent:2em;
			line-height: 1.5em;
		}
	}
	&-add-button {
		color: $orange;
		text-align: center;
		font-size: 16px;
		font-weight: bold;
	}
}
</style>
