<template>
	<div class="teamcardwrap">
<!-- 		<div class="card-head" :style="bgStyle">
			<div class="card-title-style" />
			<span class="card-title">{{name}}</span>
		</div> -->
		<div class="card-info">
			<image src="/static/yinhao.png"></image>{{info}}
		</div>
		<div class="card-tech">
			<div class="card-tech-title">主要技术方向</div>
			<div class="card-tech-content">{{tech}}</div>
		</div>
		<div class="avatar-wrap">
			<div class="avatar" :style="bgStyle"></div>
			<div class="avatar-info">
				<h5 class="avatar-info-name">{{name}}</h5>
				<div class="avatar-info-other">ying</div>
			</div>
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
	width: 260px;
	height: 450px;
	background: $white;
	border: 1px $gray solid;
	border-radius: 8px;
	box-shadow: 3px 4px 6px rgba(0,0,0,0.3);
	padding: 20px;
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
		
		//border-bottom: 1px $gray solid;
		font-size: 14px;
		font-weight: 700;
		line-height: 1.5em;
		height: 200px;
		overflow: hidden;
		image{
			width:32px ;
			height:24px;
			position: relative;
			top:5px;
			margin-right: 8px;
		}
	}
	&-tech {
		margin-top: 50px;
		&-title {
			color: $black;
			font-size: 16px;
			margin-bottom: 15px;
		}
		&-content {
			font-size: 12px;
			color: $darkgray;
		}
	}
}
.avatar-wrap {
	position: absolute;
	transform: translate(0,-150%);
	bottom: 0;
}
.avatar{
	height: 50px;
	width: 50px;
	border-radius: 50%;
	display: inline-block;
}
.avatar-info {
	display: inline-block;
	margin-left: 20px;
	&-name {
		color: $orange;
		font-size: 16px;
	}
	&-other {
		color: $darkgray;
		font-size: 13px;
	}
}
</style>
