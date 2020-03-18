<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select">{{ leftBtn }}</view>
		</nav-bar>
		<view class="main"></view>
		<view class="btn-bar">
			<submit-button msg="增加渠道" @click.native="toAddChannel"></submit-button>
		</view>
		<input-dialog ref="inputDialog" title="提示" content="哈哈，还是被你看到了..." 
			:status="show"
			@cancel="clickCancel('cancel')" @confirm="clickConfirm('confirm')">
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
				leftBtn: '<',
				show: true
			}
		},
		methods: {
			clickCancel(val) {
				console.log(val)
			},
			clickConfirm(val) {
				console.log(val)
			},
			toAddChannel() {
				console.log('dfdfdf')
				this.$refs.inputDialog.show()
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
		margin-left: 30upx;
		font-weight: 700;
	}

	.main {
		flex-grow: 1;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
