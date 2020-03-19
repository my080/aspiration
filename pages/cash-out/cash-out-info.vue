<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click.native="toBack"></view>
		</nav-bar>
		<view class="main">
			<view class="message-list">
				<view class="message-item">
					<view class="labal">
						申请时间
					</view>
					<view class="message-content">
						2020-06-01  08:08
					</view>
				</view>
				<view class="message-item">
					<view class="labal">
						到账时间
					</view>
					<view class="message-content">
						2020-06-01  08:08
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
			
			<view class="message-list" style="padding-bottom: 0upx;">
				<view class="message-item">
					<view class="labal">
						提现户名
					</view>
					<view class="message-content">
						吉林学梯
					</view>
				</view>
				<view class="message-item">
					<view class="labal">
						提现账号
					</view>
					<view class="message-content">
						213***5135
					</view>
				</view>
			</view>
			
			<view class="message-list" style="padding-bottom: 0upx;">
				<view class="message-item">
					<view class="labal">
						税费税率
					</view>
					<view class="message-content">
						0.02%
					</view>
				</view>
				<view class="message-item">
					<view class="labal">
						代扣税费
					</view>
					<view class="message-content">
						￥200.00
					</view>
				</view>
				<view class="message-item">
					<view class="labal">
						到账金额
					</view>
					<view class="message-content">
						￥499,980.00
					</view>
				</view>
			</view>
			
			<view class="message-list">
				<view class="message-item">
					<view class="message-content remarks">
						备注：打款成功后实际到账时间可能因为银行等因素出现延期，请耐心等待
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
				barTitle: "提现详情",
				title: '能上的大学'
			}
		},
		methods: {
			toBack() {
				uni.navigateTo({
					url: './cash-out-list'
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
		background: #FFFFFF;
	}

	.address_select {
		margin-left: 44upx;
		background: url(../../static/img/pic17.png) no-repeat center;
		background-size: 20upx;
		width: 20upx;
		height: 32upx;
	}
	
	.message-list {
		display: flex;
		flex-direction: column;
		padding: 44upx;
		background: #FFFFFF;
		margin-bottom: 20upx;
	}
	
	.message-list:last-child {
		flex-grow: 1;
		margin-bottom: 0upx;
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
	
	.remarks {
		font-family: OPPOSans-R;
		font-size: 24upx !important;
		color: #909399 !important;
		line-height: 40upx !important;
		flex-grow: 1;
	}

	.main {
		flex-grow: 1;
		background: #F3F7FA;
		display: flex;
		flex-direction: column;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
