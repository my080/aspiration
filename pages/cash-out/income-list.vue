<template>
	<view class="content">
		<nav-bar :title="barTitle" @click.native="toBack">
			<view slot="left" class="address_select"></view>
		</nav-bar>
		<view class="main">
			<view class="date-bar">
				<dy-date timeType="day" minSelect="1900/01/01" placeholder="请选择日期"></dy-date>
			</view>
			
			<uni-list>
			    <uni-list-item title="能上的大学" note="6月1日  08:08" :show-badge="true" badge-text="+12" @click.native="toIncomeInfo"></uni-list-item>
			    <uni-list-item title="推测会员VIP" note="6月1日  07:08" :show-badge="true" badge-text="+12" @click.native="toIncomeInfo"></uni-list-item>
				<uni-list-item title="能上的大学" note="6月1日  07:08" :show-badge="true" badge-text="+12" @click.native="toIncomeInfo"></uni-list-item>
				<uni-list-item title="推测会员VIP-补" note="6月1日  07:08" :show-badge="true" badge-text="+12" @click.native="toIncomeInfo"></uni-list-item>
				<uni-list-item title="能上的大学-退款" note="6月1日  07:08" :show-badge="true" badge-text="+12" @click.native="toIncomeInfo"></uni-list-item>
				<uni-list-item title="能上的大学" note="6月1日  07:08" :show-badge="true" badge-text="+12" @click.native="toIncomeInfo"></uni-list-item>
			</uni-list>
		</view>
	</view>
</template>

<script>
	import NavBar from "@/components/zhouWei-navBar"
	import UniList from "@/components/uni-list/uni-list.vue"
	import UniListItem from "@/components/uni-list-item/uni-list-item.vue"
	import DyDate from '@/components/dy-Date/dy-Date.vue'

	export default {
		name: 'empty-channel',
		components: {
			'nav-bar': NavBar,
			'uni-list': UniList,
			'uni-list-item': UniListItem,
			'dy-date': DyDate
		},
		data() {
			return {
				barTitle: "收入明细"
			}
		},
		methods: {
			toBack() {
				uni.navigateTo({
					url: '../index/index'
				})
			},
			toIncomeInfo() {
				uni.navigateTo({
					url: './income-info'
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
		flex-grow: 1;
	}
	
	.date-bar {
		margin-top: 48upx;
		padding: 26upx 30upx;
		background: #F3F7FA;
		font-family: OPPOSans-R;
		font-size: 26upx;
		color: #303133;
	}

	.btn-bar {
		padding-bottom: 64upx;
	}
</style>
