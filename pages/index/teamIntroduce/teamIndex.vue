<template>
	<div>
		<PageHeader title="项目组介绍" :isshowlogo="false"></PageHeader>
		<div class="content" v-if="isReady">
			<p class="animated fadeInUp" style="animation-delay: 0.5s;">我们是一个以项目实践为中心的团队</p>
			</br>
			<p class="animated fadeInUp" style="animation-delay: 1.5s;">让我们来看看现在有什么项目组吧</p>
		</div>
		<div class="drop" @click="handleClick">
			<DropUpArrow></DropUpArrow>
		</div>
	</div>
</template>

<script>
import PageHeader from "@/components/PageHeader.vue"
import DropUpArrow from "@/components/DropUpArrow.vue"
	export default {
		components:{
			PageHeader,
			DropUpArrow
		},
		props : {
			'isReady': Boolean,
		},
		data() {
			return {
				
			};
		},
		methods:{
			handleClick(){
				uni.reLaunch({
					url: "/pages/index/teamIntroduce/introduce"
				})
			}
		}
	}
</script>

<style lang="scss">
@import "@/style/Animate.scss";
.content {
	font-size: 20px;
	color: $black;
	position: absolute;
	width: 100%;
	top: 50%;
	//left: 50%;
	transform: translate(0,-50%);
	text-align: center;
	//justify-content: center;
	//align-items: center;
}

.drop{
	display: flex;
	position: absolute;
	bottom: 30px;
	left: 50%;
	transform: translate(-50%,-50%);
	justify-content: center;
}
</style>
