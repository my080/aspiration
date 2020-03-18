<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click.native="toBack"></view>
		</nav-bar>
		<view class="main"></view>
		<view class="btn-bar">
			<submit-button msg="我知道了" @click.native="toAddChannel"></submit-button>
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
			toAddChannel() {
				uni.navigateTo({
					url: '../index/index'
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

	.main {
		flex-grow: 1;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
