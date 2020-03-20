<template>
	<view class="xy-dialog" :class="{ 'xy-dialog__show': isShow }" @touchmove.stop.prevent="bindTouchmove">
		
		<view class="xy-dialog__container">
			
			<view class="close" @click.native="closeDialog"></view>
			
			<view class="btn-area">
				<button class="create-btn" @click.native="toBusiness">我是企业</button>
				<button class="create-btn" @click.native="toPersonel">我是个人</button>
			</view>
			
		</view>
		
		<view class="xy-dialog__mask"></view>
	</view>
</template>

<script>
	
	import UniSInput from '../field/input.vue'
	
	export default {
		components: {
			'uni-s-input': UniSInput
		},
		name: 'input-dialog',
		props: {
			// 是否显示弹出框
			status: {
				type: Boolean,
				default: false
			}
		},
		data() {
			return {
				isShow: false
			}
		},
		watch: {
			show(val) {
				this.isShow = val
			}
		},
		methods: {
			// 禁止穿透
			bindTouchmove() {},

			show() {
				this.isShow = true;
			},

			addChannel() {
				this.$emit('to-new-channel')
			},

			// 关闭弹窗
			closeDialog() {
				this.isShow = false;
				this.$emit('close')
			},
			
			toBusiness() {
				this.$emit('to-business')
			},
			
			toPersonel() {
				this.$emit('to-personal')
			}
		}
	}
</script>

<style platform="mp-weixin" lang="scss" scoped>
	.xy-dialog {
		position: fixed;
		visibility: hidden;
		width: 100%;
		height: 100%;
		top: 0;
		right: 0;
		bottom: 0;
		left: 0;
		z-index: 1500;
		transition: visibility 200ms ease-in;
		
		.btn-area {
			width: 100%;
			margin-left: auto;
			margin-right: auto;
			height: 320upx;
			display: flex;
			flex-direction: column;
			justify-content: center;
		}
		
		.create-btn {
			margin-top: 26upx;
			width: 294upx;
			height: 76upx;
			color: #FFFFFF;
			background-color: #6481FD;
			font-family: OPPOSans-M;
			font-size: 32upx;
			text-align: center;
			line-height: 76upx;
			border-radius: 38upx;
			letter-spacing: 1upx;
			border: 1upx solid #FFFFFF;
		}
		
		.xy-dialog__container {
			width: 658upx;
			height: 424upx;
			background-image: linear-gradient(143deg, #3DACFF 0%, #796BFC 100%);
			border-radius: 11px;
			border-radius: 11px;
			padding: 30upx;
		}
		
		.close {
			background: url(../../../../static/img/pic16.png) no-repeat center;
			width: 45upx;
			height: 45upx;
			background-size: 30upx;
			float: right;
		}

		&.xy-dialog__show {
			visibility: visible;
		}

		&__container {
			position: absolute;
			z-index: 1010;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
			transition: transform 0.3s;
			background-color: #fff;
			overflow: hidden;
			opacity: 1;
			transition: opacity 200ms ease-in;
			padding-top: 30upx;
		}
		
		&__mask {
			display: block;
			position: absolute;
			z-index: 1000;
			top: 0;
			left: 0;
			right: 0;
			bottom: 0;
			width: 100%;
			height: 100%;
			transition: opacity 200ms ease-in;
			background: rgba($color: #000000, $alpha: 0.8);
		}

		&__show {

			.xy-dialog__container,
			.xy-dialog__mask {
				opacity: 1;
			}
		}
	}
</style>
