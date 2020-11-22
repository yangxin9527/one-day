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
	*{
		box-sizing: border-box;
	}
	.od-input{
		display: flex;
		margin: 0 20px;
		height: 40px;
		background: #f3f3f3;
		padding: 10px;
		font-size: 12px;
	}
	.my-icon {
		width: 100%;
		height: 100%;
		background: url('@/static/icon/0.png') no-repeat;
		background-size: cover;
	}
	
	.my-icon-1 {
		background-image: url('@/static/icon/1.png');
	}
	
	.my-icon-2 {
		background-image: url('@/static/icon/2.png');
	}
	
	.my-icon-3 {
		background-image: url('@/static/icon/3.png');
	}
	
	.my-icon-4 {
		background-image: url('@/static/icon/4.png');
	}
	
	.my-icon-5 {
		background-image: url('@/static/icon/5.png');
	}
	
	.my-icon-6 {
		background-image: url('@/static/icon/6.png');
	}
	
	.my-icon-7 {
		background-image: url('@/static/icon/7.png');
	}
	
	.my-icon-8 {
		background-image: url('@/static/icon/8.png');
	}
	
	.my-icon-9 {
		background-image: url('@/static/icon/9.png');
	}
</style>
