<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click="toBack"></view>
		</nav-bar>
		
		<view class="main"></view>
		
		<view class="btn-bar">
			<submit-button msg="点击查看" @click.native="toAddChannel"></submit-button>
		</view>
		
		<input-dialog ref="inputDialog" title="提示"
			:status="show">
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
				barTitle: "新增渠道",
				show: true
			}
		},
		methods: {
			toAddChannel() {
				uni.navigateTo({
					url: './my-channel'
				})
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
