<script>
	export default {
		onLaunch: function() {
			console.log('App Launch');
			//移除头部栏
			if(document.getElementsByTagName('uni-page-head')[0]){
				document.getElementsByTagName('uni-page-head')[0].remove();
			}
		},
		onShow: function() {
			console.log('App Show')
			if(document.getElementsByTagName('uni-page-head')[0]){
				document.getElementsByTagName('uni-page-head')[0].remove();
			}
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/* 加上因为css背景图片的相对路径 */
	/*每个页面公共css */
* {
	margin: 0;
	padding: 0;
}
	
page{
	// background: $purple;
	height: 100%;
	width: 100%;
}

page {
	background-image: url("./static/image/bg.jpg");
	background-repeat:no-repeat; 
	background-size:100% 100%;
	-moz-background-size:100% 100%;
}
</style>
