<template>
	<view class="home-wrap">
		<view class="container-title">
			<text>每日打卡</text>
			<image class="add" src="/static/add.png"  @click="add" ></image>
		</view>
		<view class="clock-in-list">
			<view class="item" v-for='item in clockinList'>
				<clockin-img class="item-img" :code='item.code'></clockin-img>
				<text>{{item.name}}</text>
			</view>
		
			
		</view>
		<!-- <view class="container-title">
			<text>待办</text>
			<image class="add" src="/static/add.png" ></image>
		</view> -->
		
	</view>
</template>

<script>
	export default {
		data() {
		
			return {
				clockinList:[]
			}
		},
		onShow(){
			let clockin = uni.getStorageSync('clockin');
			let clockinList = [];
			if(clockin){
				clockinList = JSON.parse(clockin)
			}
			this.clockinList=clockinList;
		},
		methods:{
			add(){
				console.log(1);
				uni.navigateTo({
				    url: '/pages/add-clock-in/add-clock-in'
				});
			}
		}
		
	}
</script>

<style lang='scss' scoped>
	.container-title{
		display: flex;
		padding: 15px;
		align-items: center;
		font-size: 20px;
		.add{
			width: 30px;
			height: 30px;
		}
	}
	.clock-in-list{
		display: flex;
		flex-wrap: wrap;
		.item{
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
		}
		.item-img{
		
			width: 100px;
			height: 100px;
		}
	}

</style>
