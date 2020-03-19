<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click.native="toBack"></view>
		</nav-bar>
		<view class="main">
			<view>
				
			</view>
			<view>
				
			</view>
			<view>
				
			</view>
			<view>
				
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

<style platform="mp-weixin">
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
		padding: 26upx 30upx;
		background: #F3F7FA;
		font-family: OPPOSans-R;
		font-size: 26upx;
		color: #303133;
		text-align: center;
	}
	
	.message-bar .title {
		ont-family: OPPOSans-R;
		font-size: 28upx;
		color: #303133;
	}
	
	.message-bar .price {
		font-family: OPPOSans-H;
		font-size: 28upx;
		color: #303133;
		font-weight: 700;
	}

	.main {
		flex-grow: 1;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
