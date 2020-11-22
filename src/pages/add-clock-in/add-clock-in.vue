<template>
	<view>
			<view class="choose-img">
				<clockin-img :code='codeIndex'></clockin-img>
			</view>
			<view class="list-wrap" >
				<view class="item" v-for="item in list"  @click='handleIndex(item)' data-id='item'>
					<clockin-img :code='item'></clockin-img>
				</view>
			</view>
			
			<input type="text" v-model="inputValue" class="od-input" placeholder="跑步,吃药,记账,洗衣服" />
			<button type="default" @click='submit' >新增</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				codeIndex:0,
				inputValue:'',
				list:[0,1,2,3,4,5,6,7,8,10]
			}
		},
		methods: {
			handleIndex(index){
				this.codeIndex=index
			},
			submit(){
				console.log('submit'+this.inputValue)
				let clockin = [];
				if(uni.getStorageSync('clockin')){
					clockin = JSON.parse(uni.getStorageSync('clockin'))
				}
				clockin.push({
					code:this.codeIndex,
					name:this.inputValue,
					completed:0
				})
				uni.setStorageSync('clockin',JSON.stringify(clockin));
				uni.showToast({
					title:'添加成功',
					mask:true,
					duration:1000,
					complete:()=>{
						console.log(111)
						uni.navigateBack();
					}
				})
				
			}
		}
	}
</script>

<style lang='scss' scoped>
	.choose-img{
		width: 81px;
		height: 81px;
		margin: 0 auto;
	}
	.list-wrap{
		display: flex;
		flex-wrap: wrap;
		padding: 8px;
		margin: 0 10px ;
		border: 1px solid;
		.item{
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			padding: 5px;
			width: 50px;
			height: 50px;
		}
	}
	.od-input{
		margin:10px  20px;
	}
</style>
