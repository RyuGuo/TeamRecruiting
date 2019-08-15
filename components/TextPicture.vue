<template>
	<div>
		<div v-if="type==0" class="img-wrap">
			
		</div>
		<div v-if="type==1" class="img-wrap">
			<div class="img-wrap-left">
				<image :src="imgList[0]" mode=""></image>
			</div>
			<div class="img-wrap-right">
				<image :src="imgList[1]" mode=""></image>
				<image :src="imgList[2]" mode=""></image>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			type: Number,
			imgList: Array,
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.img-wrap {
	width: 100%;
	display: flex;
	justify-content: space-around;
	line-height: 0px;
	&-left {
		width: 111px;
		height: 196px;
		image {
			width: 111px;
			height: 196px;
		}
	}
	&-right{
		width: 191px;
		height: 196px;
		image {
			width: 100%;
			height: 89px;
		}
	}
	image {
		border-radius: 10px;
		margin-bottom: 18px;
	}
}
</style>
