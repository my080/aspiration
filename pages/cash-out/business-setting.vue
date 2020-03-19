<template>
	<view class="content">
		<nav-bar :title="barTitle">
			<view slot="left" class="address_select" @click.native="toBack"></view>
		</nav-bar>
		
		<view class="main">
			
			<view class="input-item">
				<view class="labal">
					企业名称：
				</view>
				<m-input placeholder="企业全称"></m-input>
			</view>
			
			<view class="input-item">
				<view class="labal">
					开户银行：
				</view>
				<m-input placeholder="详情到支行"></m-input>
			</view>
			
			<view class="input-item">
				<view class="labal">
					银行账号：
				</view>
				<m-input placeholder="银行卡号"></m-input>
			</view>
			
			<view class="input-item">
				<view class="labal">
					营业执照：
				</view>
			</view>
			
		</view>
		
		<view class="btn-bar">
			<submit-button msg="提交审核" @click.native="submit"></submit-button>
		</view>
	</view>
</template>

<script>
	import NavBar from "@/components/zhouWei-navBar"
	import SubmitButton from '@/components/submit-button/submit-button.vue'
	import mInput from './components/field/input.vue'

	export default {
		name: 'empty-channel',
		components: {
			'nav-bar': NavBar,
			'submit-button': SubmitButton,
			'm-input': mInput
		},
		data() {
			return {
				barTitle: "设置企业提现账户"
			}
		},
		methods: {
			toBack() {
				uni.navigateTo({
					url: '../index/index'
				})
			},
			submit() {
				uni.navigateTo({
					url: '../index/index'
				})
			}
		}
	}
</script>

<style scoped>
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

	.main {
		justify-content: start;
		flex-grow: 1;
		padding: 80upx 44upx;
	}
	
	.input-item {
		display: flex;
	}
	
	.input-item .labal {
		width: 200upx;
		font-family: OPPOSans-R;
		font-size: 26upx;
		color: #909399;
		line-height: 80upx;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
