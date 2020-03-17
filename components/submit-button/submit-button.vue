<template>
	<button class="btn-bg">{{ message }}</button>
</template>

<script>
	export default {
		name: 'submit-button',
		props: ['msg'],
		data() {
			return {
				message: this.$props['msg']
			}
		}
	}
</script>

<style>
	.btn-bg {
		font-family: 'OPPOSans-M';
		font-size: 32upx;
		line-height: 92upx;
		height: 92upx;
		border-radius: 46upx;
		color: #FFFFFF;
		width: 662upx;
		background: linear-gradient(143deg, #3DACFF 0%, #796BFC 100%);
	}
	.btn-bg:hover {
		background: linear-gradient(143deg, #4EBDFF 0%, #8A7CFD 100%);
	}
</style>
