<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click="toBack"></view>
		</nav-bar>
		<view class="main">
			<view class="message-list">
				
				<view class="message-item">
					<view class="labal">
						渠道名称
					</view>
					<view class="message-content">
						高三网
					</view>
				</view>
				
				<view class="message-item">
					<view class="labal">
						申请时间
					</view>
					<view class="message-content">
						2020-06-01  08:08
					</view>
				</view>
				
			</view>
			
			<view class="channels">
				
				<view class="icon">
					<view class="H5-icon item"></view>
					<view class="title">H5</view>
				</view>
				
				<view class="icon">
					<view class="PC-icon item"></view>
					<view class="title">PC端</view>
				</view>
				
				<view class="icon">
					<view class="er-icon item"></view>
					<view class="title">二维码</view>
				</view>
				
				<view class="icon">
					<view class="wx-icon item"></view>
					<view class="title">微信小程序</view>
				</view>
				
				<view class="icon">
					<view class="baidu-icon item"></view>
					<view class="title">百度小程序</view>
				</view>
				
				<view class="icon">
					<view class="zhi-icon item"></view>
					<view class="title">支付宝小程序</view>
				</view>
				
			</view>
			
		</view>
		
		<view class="btn-bar">
			<submit-button msg="点击查看" @click.native="toAddChannel"></submit-button>
		</view>
		
		<image-dialog ref="imageDialog" :status="imageShow">
			
		</image-dialog>
	</view>
</template>

<script>
	import NavBar from "@/components/zhouWei-navBar"
	import SubmitButton from '@/components/submit-button/submit-button.vue'
	import InputDialog from './components/dialog/input.vue'
	import ImageDialog from './components/dialog/image.vue'

	export default {
		name: 'empty-channel',
		components: {
			'nav-bar': NavBar,
			'submit-button': SubmitButton,
			'input-dialog': InputDialog,
			'image-dialog': ImageDialog
		},
		data() {
			return {
				barTitle: "新增渠道",
				show: true,
				imageShow: true
			}
		},
		methods: {
			toAddChannel() {
				this.$refs.imageDialog.show()
				// uni.navigateTo({
				// 	url: './my-channel'
				// })
			},
			toBack() {
				// uni.navigateTo({
				// 	url: './my-channel'
				// })
				uni.navigateTo({
					url: './empty-channel'
				})
			}
		}
	}
</script>

<style platform="mp-weixin" scoped>
	.content {
		display: flex;
		flex-direction: column;
		height: 100vh;
	}

	.address_select {
		margin-left: 44upx;
		background: url(../../static/img/pic17.png) no-repeat center;
		background-size: 20upx;
		width: 20upx;
		height: 32upx;
	}

	.main {
		flex-grow: 1;
	}
	
	.message-bar {
		margin-top: 48upx;
		padding: 26upx 36upx;
		background: #F3F7FA;
		color: #303133;
		text-align: center;
		display: flex;
		flex-direction: column;
	}
	
	.message-bar .title {
		font-family: OPPOSans-R;
		font-size: 28upx;
		color: #303133;
	}
	
	.message-bar .price {
		font-family: OPPOSans-H;
		font-size: 28upx;
		color: #303133;
		font-weight: 700;
		margin-top: 20upx;
	}
	
	.message-list {
		display: flex;
		flex-direction: column;
		padding: 44upx 44upx 0upx 44upx;
		background: #F3F7FA;
	}
	
	.message-list .message-item {
		display: flex;
		height: 80upx;
	}
	
	.message-list .message-item .labal {
		width: 160upx;
		min-width: 160upx;
		font-family: OPPOSans-R;
		font-size: 26upx;
		color: #909399;
		line-height: 42upx;
	}
	
	.message-list .message-item .message-content {
		font-family: OPPOSans-M;
		font-size: 28upx;
		color: #303133;
		flex-grow: 1;
		letter-spacing: 1.2px;
		line-height: 42upx;
		word-break: break-all;
		font-weight: 600;
	}
	
	.channels .icon .item {
		width: 207upx;
		height: 148upx;
		background-size: 74upx;
		/* border: 6upx solid #F0F3F5; */
		border-radius: 12upx;
		margin: auto;
		border: 6upx solid #FFFFFF;
	}
	
	.channels .icon .item:hover {
		border: 6upx solid #F0F3F5;
		border-radius: 12upx;
	}
	
	.H5-icon {
		background: url(../../static/img/pic18.png) no-repeat center;
	}
	
	.PC-icon {
		background: url(../../static/img/pic19.png) no-repeat center;
	}
	
	.er-icon {
		background: url(../../static/img/pic20.png) no-repeat center;
	}
	
	.wx-icon {
		background: url(../../static/img/pic21.png) no-repeat center;
	}
	
	.baidu-icon {
		background: url(../../static/img/pic22.png) no-repeat center;
	}
	
	.zhi-icon {
		background: url(../../static/img/pic23.png) no-repeat center;
	}
	
	.channels {
		display: flex;
		flex-wrap: wrap;
		padding: 60upx 40upx;
	}
	
	.channels .icon {
		width: 33%;
		text-align: center;
	}
	
	.channels .icon .title {
		font-family: OPPOSans-R;
		font-size: 26upx;
		color: #909399;
		text-align: center;
		margin-top: 10upx;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
