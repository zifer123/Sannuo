<script>
export default {
	onLaunch: function() {
		uni.login({
		  provider: 'weixin',
		  success: function (loginRes) {
		    console.log(loginRes);
		  }
		});
	},
	onShow: function() {
		console.log('App Show');
	},
	onHide: function() {
		console.log('App Hide');
	}
};
</script>

<style>
/*每个页面公共css */ 
page {
	height: 100%;
	font-size: 14px;
	letter-spacing: 1px;
}
</style>
