<template>
    <view class="container">
        <input class="s-input" :type="type" @input="inputChange" :id="id" placeholder-class="placeholder-class" :placeholder="placeholder" :value="value">
        <!-- <view v-if="value" class="clear-icon" @click="restInput">x</view> -->
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
        placeholderClass: { // placeholder的class，方便自定义placeholder样式
            type: String,
            default: 'input-placeholder'
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
        }
    },
    data () {
        return {
            value: ''
        }
    },
    methods: {
        restInput () {
            this.value = ''
            this.$emit('inputValue', {
                id: this.id,
                value: this.value
            })
        },
        inputChange (e) {
            this.value = e.detail.value
            this.$emit('inputValue', {
                id: this.id,
                value: e.detail.value
            })
        }
    },
    created () {
        this.value = this.initValue
        this.$emit('inputValue', {
            id: this.id,
            value: this.initValue
        })
    }
}
</script>

<style lang="scss" scoped>
    .container {
        width: 60vh;
        display: flex;
        flex-direction: row;
        display: flex;
        align-items: center;
    }
    .label-title {
        font-size: 32upx;
    }
    .s-input {
		padding-top: 18upx;
		padding-bottom: 18upx;
        padding-left: 20upx;
        width: 100%;
		border-bottom: 1upx solid rgba($color: #979797, $alpha: 0.2);
    }
    .clear-icon {
        width: 30upx;
        height: 30upx;
        border-radius: 50%;
        background: #CECFDA;
        color: #ffffff;
        font-size: 20upx;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .input-placeholder {
        font-size: 32upx;
        color: #CECFDA;
    }
	.placeholder-class {
		font-family: OPPOSans-R;
		font-size: 28upx;
		color: #C0C4CC;
	}
</style>
