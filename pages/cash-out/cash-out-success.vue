<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click.native="toBack"></view>
		</nav-bar>
		<view class="main">
			<view class="carpet">
				<view class="title">
					1、提现门槛
				</view>
				<view class="desc-message">
					<view>
						a. 提现金额需大于等于50元，上不封顶
					</view>
					<view>
						b. 每个月最多可申请4次提现
					</view>
				</view>
			</view>
			
			<view>
				<view class="title">
					2、提现须知
				</view>
				<view class="desc-message">
					<view class="item">
						a. 商品确认收货后，有7天的退换货周期。待周期结束，佣金进入可提现账户，方可申请提现。未结算的佣金不能提现
					</view>
					<view class="item">
						b. 满足提现门槛的佣金即可发起提现，提现后等待财务人员受理,工作日24小时内到账，遇节假日顺延
					</view>
					<view class="item">
						c. 已有待处理申请未被受理时，无法发起下一笔提现需求，请耐心等待
					</view>
				</view>
			</view>
		</view>
		<view class="btn-bar">
			<submit-button msg="我知道了" @click.native="toCashOut"></submit-button>
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
				barTitle: "提现说明"
			}
		},
		methods: {
			toBack() {
				// uni.navigateTo({
				// 	url: './my-channel'
				// })
				uni.navigateTo({
					url: '../index/index'
				})
			},
			toCashOut() {
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
	
	.carpet {
		margin-bottom: 32upx;
	}
	
	.title {
		font-family: OPPOSans-B;
		font-size: 36upx;
		color: #303133;
		font-weight: 800;
		margin-bottom: 36upx;
	}
	
	.desc-message {
		font-family: OPPOSans-R;
		font-size: 28upx;
		color: #00002A;
		line-height: 50upx;
		font-weight: 300;
	}
	
	.desc-message .item {
		margin-bottom: 32upx;
	}

	.main {
		flex-grow: 1;
		padding: 80upx 44upx;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
