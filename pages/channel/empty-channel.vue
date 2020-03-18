<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click.native="toBack"></view>
		</nav-bar>
		
		<!-- #ifdef H5 -->
		<view class="main">
			<view class="infor">
				尚未配置
			</view>
		</view>
		<!-- #endif -->
		
		<!-- #ifdef MP-WEIXIN -->
		<view class="main">
			<image class="img-msg" platform="mp-weixin" src="../../static/img/pic15.png" mode=""></image>
			<view class="img-infor">
				尚未配置
			</view>
		</view>
		<!-- #endif -->
		
		<view class="btn-bar">
			<submit-button msg="增加渠道" @click.native="toAddChannel"></submit-button>
		</view>
		<input-dialog ref="inputDialog" title="提示"
			:status="show" @to-new-channel="toNewChannel">
		</input-dialog>
	</view>
</template>

<script>
	import NavBar from "@/components/zhouWei-navBar"
	import SubmitButton from '@/components/submit-button/submit-button.vue'
	import InputDialog from './components/dialog/input.vue'

	export default {
		name: 'empty-channel',
		components: {
			'nav-bar': NavBar,
			'submit-button': SubmitButton,
			'input-dialog': InputDialog
		},
		data() {
			return {
				barTitle: "我的渠道",
				show: true
			}
		},
		methods: {
			toAddChannel() {
				this.$refs.inputDialog.show()
			},
			toNewChannel() {
				uni.navigateTo({
					url: './new-channel'
				})
			},
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

	.main {
		background: url(../../static/img/pic15.png) no-repeat;
		background-size: 306upx;
		background-position-x: center;
		background-position-y: 364upx;
		flex-grow: 1;
	}
	
	.img-msg {
		margin: 364upx auto auto auto;
		width: 306upx;
		height: 272upx;
		display: block;
	}
	
	.infor {
		font-family: OPPOSans-R;
		font-size: 26upx;
		color: #C0C4CC;
		text-align: center;
		margin-top: 676upx;
	}
	
	.img-infor {
		font-family: OPPOSans-R;
		font-size: 26upx;
		color: #C0C4CC;
		text-align: center;
		margin-top: 40upx;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
