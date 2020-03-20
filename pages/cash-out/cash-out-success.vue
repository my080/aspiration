<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click.native="toBack"></view>
		</nav-bar>
		<view class="main">
			<view class="message-bar">
				<!-- <view class="title">
					{{ title }}
				</view> -->
				<view class="price">
					{{ price }}
				</view>
			</view>
			
			<view class="message-list">
				<view class="message-item">
					<view class="labal">
						成交时间
					</view>
					<view class="message-content">
						2020-06-01  08:08
					</view>
				</view>
				
				<view class="message-item">
					<view class="labal">
						申请状态
					</view>
					<view class="message-content">
						提现中
					</view>
				</view>
				
				<view class="message-item">
					<view class="labal">
						预计到账
					</view>
					<view class="message-content">
						3-8个工作日
					</view>
				</view>
				
				<view class="message-item">
					<view class="labal">
						订单号码
					</view>
					<view class="message-content">
						1000049901202202170123378494558
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import NavBar from "@/components/zhouWei-navBar"

	export default {
		name: 'empty-channel',
		components: {
			'nav-bar': NavBar
		},
		data() {
			return {
				barTitle: "账单详情",
				title: '能上的大学',
				price: '￥5000,000'
			}
		},
		methods: {
			toBack() {
				uni.navigateTo({
					url: '../index/index'
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

	.main {
		flex-grow: 1;
	}
	
	.message-list {
		display: flex;
		flex-direction: column;
		padding: 44upx;
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
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
