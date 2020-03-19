<template>
	<view class="main">
		<nav-bar :title="title">
			<view slot="left"></view>
		</nav-bar>
		<view class="price-bg">
			
			<!-- #ifdef H5 -->
			<view class="price-status">
				<view class="left">
					<view class="evaluate">
						估计收入
					</view>
					<view class="price">{{ RMB }}</view>
				</view>
				<view class="right">
					<button class="cash-out-btn" @click.native="toCashOut">提现</button>
				</view>
			</view>
			<!-- #endif -->
			
			<!-- #ifdef MP-WEIXIN -->
			
			<view class="price-status-wx">
				
				<image class="price-status-img" src="../../static/img/pic8.png" mode="">
					
				</image>
				
				<view class="price-info">
					<view class="left">
						<view class="evaluate">
							估计收入
						</view>
						<view class="price">{{ RMB }}</view>
					</view>
					<view class="right">
						<button class="cash-out-btn" @click.native="toCashOut">提现</button>
					</view>
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
		
		<capacity-dialog ref="capacityDialog" title="提示"
			:status="show" @to-new-channel="toNewChannel" @to-business="toBusiness" @to-personal="toPersonal">
		</capacity-dialog>
	
	</view>
</template>

<script>
	import NavBar from "@/components/zhouWei-navBar"
	import CapacityDialog from './components/dialog/capacity.vue'

	export default {
		components: {
			'nav-bar': NavBar,
			'capacity-dialog': CapacityDialog
		},
		name: "index",
		data() {
			return {
				title: '我的收益',
				RMB: '￥3000.00',
				show: false
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
			toCashOut() {
				this.$refs.capacityDialog.show()
			},
			toNewChannel() {
				
			},
			toChannel() {
				uni.navigateTo({
					url: '../channel/empty-channel'
				})
				// uni.navigateTo({
				// 	url: '../channel/my-channel'
				// })
			},
			toBusiness() {
				this.$refs.capacityDialog.closeDialog()
				uni.navigateTo({
					url: '../cash-out/business-setting'
				})
			},
			toPersonal() {
				this.$refs.capacityDialog.closeDialog()
				uni.navigateTo({
					url: '../cash-out/personal-setting'
				})
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
		background: url(../../static/img/pic8.png) no-repeat center;
		background-repeat: no-repeat;
		background-size: 718upx;
		margin-left: auto;
		margin-right: auto;
		border-radius: 12upx;
		width: 718upx;
		height: 202upx;
		display: flex;
		
		.left {
			display: flex;
			flex-direction: column;
			flex-grow: 1;
			justify-content: center;
			
			.evaluate {
				padding-left: 48upx;
				text-align: left;
				opacity: 0.6;
				font-family: OPPOSans-R;
				font-size: 28upx;
				color: #FFFFFF;
				margin-bottom: 12upx;
			}
			
			.price {
				padding-left: 40upx;
				text-align: left;
				font-family: OPPOSans-H;
				font-size: 44upx;
				color: #FFFFFF;
			}
		}
		
		.right {
			display: flex;
			width: 206upx;
			align-items: center;
		}
	}
	
	.cash-out-btn {
		font-family: OPPOSans-R;
		font-size: 28upx;
		color: #FFFFFF;
		text-align: center;
		width: 134upx;
		height: 48upx;
		line-height: 46upx;
		background: #786AFC;
		opacity: 0.6;
		border: 1upx solid #FFFFFF;
		border-radius: 24px;
	}
	
	.cash-out-btn:hover {
		opacity: 0.8;
	}
	
	.price-status-wx {
		background: #ffffff;
		width: 100vh;
		
		.price-info {
			display: flex;
			position: absolute;
			width: 718upx;
			height: 202upx;
			top: 128upx;
			left: 0;
			right: 0;
			margin-left: auto;
			margin-right: auto;
			
			.left {
				display: flex;
				flex-direction: column;
				flex-grow: 1;
				justify-content: center;
				
				.evaluate {
					padding-left: 48upx;
					text-align: left;
					opacity: 0.6;
					font-family: OPPOSans-R;
					font-size: 28upx;
					color: #FFFFFF;
					margin-bottom: 12upx;
				}
				
				.price {
					padding-left: 40upx;
					text-align: left;
					font-family: OPPOSans-H;
					font-size: 44upx;
					color: #FFFFFF;
				}
			}
			
			.right {
				display: flex;
				width: 206upx;
				align-items: center;
			}	
		}
	}
	
	.price-status-img {
		width: 718upx;
		height: 202upx;
		display: block;
		margin-left: auto;
		margin-right: auto;
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
