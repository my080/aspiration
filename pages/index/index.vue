<template>
	<view class="main">
		<nav-bar :title="title">
			<view slot="left"></view>
		</nav-bar>
		<view class="price-bg">
			
			<!-- #ifdef H5 -->
			<view class="price-status">
				<view class="left">
					
					<view class="price">{{ RMB }}</view>
				</view>
				<view class="right">
					
				</view>
			</view>
			<!-- #endif -->
			
			<!-- #ifdef MP-WEIXIN -->
			
			<view class="price-status">
				
				<image class="price-status-img" src="../../static/img/pic8.png" mode="">
					
				</image>
				
				<view class="left">
					
					<view class="price">{{ RMB }}</view>
				</view>
				<view class="right">
					
				</view>
				
			</view>
			
			<!-- #endif -->
			
		</view>
		
		<view class="menu-bar">
			<view class="menu income" @click.native="toIncome">
				<!-- <view class="income">
					
				</view> -->
				收入明细
			</view>
			<view class="menu cash" @click.native="toCash">
				<!-- <view class="cash-out">
					
				</view> -->
				提现记录
			</view>
			<view class="menu channel" @click.native="toChannel">
				<!-- <view class="channel">
					
				</view> -->
				我的渠道
			</view>
		</view>
		
		<view class="order-count">

		</view>
	</view>
</template>

<script>
	import NavBar from "@/components/zhouWei-navBar"

	export default {
		components: {
			'nav-bar': NavBar
		},
		name: "index",
		data() {
			return {
				title: '我的收益',
				RMB: '￥3000'
			}
		},
		onLoad() {

		},
		methods: {
			toIncome() {
				uni.navigateTo({
					url: '../index/index'
				})
			},
			toCash() {
				uni.navigateTo({
					url: '../cash-out/cash-out-desc'
				})
			},
			toChannel() {
				uni.navigateTo({
					url: '../channel/empty-channel'
				})
				// uni.navigateTo({
				// 	url: '../channel/my-channel'
				// })
			}
		}
	}
</script>

<style lang="scss" scoped>
	.main {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background: #F3F7FA;
	}
	
	.price-bg {
		background: #ffffff;
		width: 100vh;
	}

	.price-status {
		background-image: url(../../static/img/pic8.png);
		background-repeat: no-repeat;
		background-size: 718upx;
		margin-left: auto;
		margin-right: auto;
		border-radius: 12upx;
		width: 718upx;
		height: 202upx;
		
		.left {
			
			.price {
				text-align: left;
				font-family: OPPOSans-H;
				font-size: 44upx;
				color: #FFFFFF;
				text-align: center;
			}
		}
	}
	
	.price-status-img {
		width: 718upx;
		height: 202upx;
	}
	
	.menu-bar {
		display: flex;
		width: 100vw;
		height: 118upx;
		background: #FFFFFF;
		
		// .income {
		// 	background: url(../../static/img/pic9.png) no-repeat center;
		// }
		
		// .cash-out {
		// 	display: inline-block;
		// 	width: 24upx;
		// 	height: 32upx;
		// 	background: url(../../static/img/pic10.png) no-repeat;
		// 	background-position-y: 10upx;
		// 	background-size: 24upx;
		// 	margin-right: 12upx;
		// }
		
		// .channel {
		// 	background: url(../../static/img/pic11.png) no-repeat center;
		// }
	}
	
	.menu {
		line-height: 118upx;
		font-family: OPPOSans-R;
		font-size: 28upx;
		color: #303133;
		text-align: center;
	}
	
	.income {
		width: 33%;
	}
	
	.cash {
		flex-grow: 1;
	}
	
	.channel {
		width: 33%;
	}
	
	.order-count {
		margin-top: 20upx;
	}
</style>
