<template>
	<view>
		<view class="title">
			{{ itemTitle }}
		</view>
		<view class="menu-bar">
			
		</view>
		<view class="count-list">
			
		</view>
	</view>
</template>

<script>
	export default {
		name: 'order-item',
		props: ['title', 'data'],
		data () {
			return {
				itemTitle: this.$props['title'],
				countData: this.$props['data']
			}
		}
	}
</script>

<style>
	
</style>
