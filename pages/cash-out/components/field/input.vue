<template>
	<view class="container">
		<input class="s-input" placeholder-class="field-input-placeholder" 
			placeholder-style="font-size: 26upx; opacity: 0.3; font-family: OPPOSans-R;color: #C0C4CC; text-align: right; font-weight: 300; letter-spacing: 2upx;" :id="id" :placeholder="placeholder" :type="type" :value="value"
			@input="inputChange">
		<!-- <view class="clear-icon">{{ count }}/{{ total }}</view> -->
	</view>
</template>

<script>
	export default {
		name: 'UniSInput',
		props: {
			placeholder: { // 输入框空时占位符
				type: String,
				default: '请输入'
			},
			id: { // 唯一标识符，当多个输入框时获取对应输入框的值
				type: String,
				default: 'inputValue'
			},
			type: { // 输入框类型
				type: String,
				default: 'text'
			},
			initValue: {
				type: String,
				default: ''
			},
			initCount: {
				type: Number,
				default: 0
			},
			initTotal: {
				type: Number,
				default: 20
			}
		},
		data() {
			return {
				value: ''
			}
		},
		methods: {
			restInput() {
				this.value = ''
				this.$emit('inputValue', {
					id: this.id,
					value: this.value
				})
			},
			inputChange(e) {
				this.value = e.detail.value
				this.$emit('inputValue', {
					id: this.id,
					value: e.detail.value
				})
			}
		},
		created() {
			this.value = this.initValue
			this.$emit('inputValue', {
				id: this.id,
				value: this.initValue
			})
		}
	}
</script>

<style platform="mp-weixin" lang="scss" scoped>
	.container {
		width: 100%;
		display: flex;
		flex-direction: row;
		align-items: center;
		border-bottom: 1upx rgba($color: #979797, $alpha: 0.3) solid;
		margin-left: auto;
		margin-right: auto;
	}

	.label-title {
		font-size: 32upx;
	}

	.s-input {
		padding-left: 20upx;
		width: 100%;
		text-align: right;
		font-size: 26upx;
		color: #303133;
		font-weight: 400;
		padding-top: 26upx;
		padding-bottom: 26upx;
	}

	.clear-icon {
		width: 80upx;
		height: 32upx;
		color: #ffffff;
		font-size: 24upx;
		display: flex;
		line-height: 32upx;
		opacity: 0.3;
		justify-content: center;
		align-items: center;
	}

	.field-input-placeholder {
		font-size: 26upx;
		opacity: 0.3;
		font-family: OPPOSans-R;
		color: #C0C4CC;
		text-align: right;
		font-weight: 300;
		letter-spacing: 2upx;
	}
</style>
