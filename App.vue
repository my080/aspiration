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

<style>
	/*每个页面公共css */
	page {
	  color: #333;
	  font-size: 16px;
	  background: #f8f8f8;
	  min-height: 100vh;
	  box-sizing: border-box;
	  -webkit-font-smoothing: antialiased;
	  font-family: 'PingFang SC', Helvetica, 'STHeiti STXihei', 'Microsoft YaHei', Tohoma, Arial, sans-serif;
	}
</style>
