<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select">{{ leftBtn }}</view>
		</nav-bar>
		<view class="main"></view>
		<view class="btn-bar">
			<submit-button msg="增加渠道"></submit-button>
		</view>
	</view>
</template>

<script>
	
	import NavBar from "@/components/zhouWei-navBar"
	import SubmitButton from '@/components/submit-button/submit-button.vue'
	
	export default {
		components: {
			'nav-bar': NavBar,
			'submit-button': SubmitButton
		},
		name: 'empty-channel',
		data () {
			return {
				barTitle: "我的渠道",
				leftBtn: '<'
			}
		}
	}
</script>

<style>
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
