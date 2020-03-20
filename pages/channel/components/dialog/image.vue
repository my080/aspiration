<template>
	<view class="xy-dialog" :class="{ 'xy-dialog__show': isShow }" @touchmove.stop.prevent="bindTouchmove">
		<view class="xy-dialog__mask"></view>
		<view class="xy-dialog__container">
			
			<view class="close" @click.native="closeDialog"></view>
			
			<!-- <view class="input-field"> -->
				<!-- <uni-s-input placeholder="请输入渠道名称..."></uni-s-input> -->
			<!-- </view> -->
			
			<view class="img-container">
				<!-- #ifdef MP-WEIXIN -->
					<view class="img-area">
						<image class="er-image" src="../../../../static/img/256.png" mode=""></image>
					</view>
				<!-- #endif -->
				
				<!-- #ifdef H5 -->
					<view class="img-area">
						<img class="er-image" src="../../../../static/img/256.png" alt="">
					</view>
				<!-- #endif -->
			</view>
			
			<button class="create-btn" @click.native="addChannel">保存图片</button>
		</view>
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
				
			},

			// 关闭弹窗
			closeDialog() {
				this.isShow = false;
				this.$emit('close')
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
		
		.create-btn {
			margin-top: 86upx;
			width: 280upx;
			height: 68upx;
			color: #6C87FD;
			font-family: OPPOSans-M;
			font-size: 32upx;
			text-align: center;
			line-height: 68upx;
			border-radius: 34upx;
			letter-spacing: 1upx;
		}
		
		.xy-dialog__container {
			width: 658upx;
			height: 950upx;
			background-image: linear-gradient(143deg, #3DACFF 0%, #796BFC 100%);
			border-radius: 11px;
			padding: 30upx;
		}
		
		.img-container {
			display: flex;
			justify-content: center;
		}
		
		.img-area {
			width: 412upx;
			height: 502upx;
			background: #FFFFFF;
			border-radius: 12upx;
			margin-left: auto;
			margin-right: auto;
		}
		
		.img-area .er-image {
			margin-left: auto;
			margin-right: auto;
		}
		
		.input-field {
			margin-top: 98upx;
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
			left: 50%;
			transform: translate(-50%, 178upx);
			transition: transform 0.3s;
			background-color: #fff;
			overflow: hidden;
			opacity: 0;
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
