<template>
	<div class="teamcardwrap">
		<div class="card-head" :style="bgStyle">
			<div class="card-title-style" />
			<span class="card-title">{{name}}</span>
		</div>
		<div class="card-info">
			{{info}}
		</div>
		<div class="card-tech">
			<div class="card-tech-title">主要技术方向</div>
			<div class="card-tech-content">{{tech}}</div>
		</div>
	</div>
</template>

<script>
	export default {
		props : {
			name: String,
			imgUrl: String,
			info: String,
			tech: String
		},
		data() {
			return {
				
			};
		},
		computed:{
			bgStyle(){
				return {
					'background-image': `url(${this.imgUrl})`,
					'background-repeat':'no-repeat;',
					'background-size':'100% 100%'
				}
			}
		}
	}
</script>

<style lang="scss">
.teamcardwrap {
	width: 290px;
	height: 490px;
	background: $white;
	border: 1px $gray solid;
	border-radius: 8px;
	box-shadow: 3px 4px 6px rgba(0,0,0,0.3);
}
.card {
	&-head {
		padding: 20px;
		height: 130px;
		display: flex;
		background: $purple;
		border-radius: 8px 8px 0 0;
		image {
			width: 100%;
			height: 100%;
			position: absolute;
		}
	}
	&-title {
		&-style {
			display: inline-block;
			width: 5px;
			height: 25px;
			background: $white;
			margin-right: 5px;
		}
		font-size: 20px;
		font-weight: bold;
		color: $white;
		
	}
	&-info {
		padding: 15px;
		border-bottom: 1px $gray solid;
		font-size: 14px;
	}
	&-tech {
		padding: 15px;
		&-title {
			color: $blue;
			font-size: 16px;
			margin-bottom: 15px;
		}
		&-content {
			font-size: 12px;
		}
	}
}
</style>
