<template>
	<div class="teacher">
		<div class="teacher-top">
			<img :src="teacher.imgurl" lazy-load="true"></img>
			<div class="teacher-info">
				<p class="teacher-name">{{teacher.name}}</p>
				<p class="teacher-research">研究方向: {{teacher.research}}</p>
			</div>
		</div>
		<p class="teacher-desc">{{teacher.desc}}</p>
	</div>
</template>

<script>
	export default {
		props : ['teacher'],
		data(){
			return {
				
			}
		}
	}
</script>

<style lang="scss">
.teacher {
	background: rgba(255,255,255,0.85);
	border: 1px $gray solid;
	border-radius: 8px;
	box-shadow: 3px 4px 6px rgba(0,0,0,0.3);
	padding: 20px;
	width: 210px;
	// height: 260px;
	&-top {
		display: flex;
		justify-content: space-around;
		// align-items:flex-end;
		img {
			height: 146px;
			width: 90px;
		}
	}
	&-info {
		margin-top: 30px;
		width: 100px;
	}
	&-name {
		text-align: center;
		font-family: 'STXingkai';
		color: $black;
		font-size: 26px;
		font-weight: 500;
	}
	&-research {
		font-size: 12px;
		color: $darkgray;
		margin-top: 10px;
	}
	&-desc {
		margin-top: 25px;
		font-size: 14px;
		font-weight: 700;
		color: $black;
	}
}
</style>
