<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
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
</style>
