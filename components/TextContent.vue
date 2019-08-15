<template>
	<div class="text">
		<p class="text-title">{{title}}</p>
		<div class="text-content">
			<p>{{maincontent}}</p>
			<div class="text-add-button" @click="handleShowAdd" v-if="isshowadd==false">read more</div>
			<p v-if="isshowadd==true" class="animated fadeIn">{{addcontent}}</p>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			title: String,
			maincontent: String,
			addcontent: String,
		},
		data() {
			return {
				isshowadd: false,
			};
		},
		methods:{
			handleShowAdd() {
				this.isshowadd = true 
			}
		}
	}
</script>

<style lang="scss" scoped>
@import "../style/text.scss";
@import "@/style/Animate.scss";
.text{
	&-content {
		p {
			color: $white;
			font-size: 16px;
			text-indent:2em;
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
