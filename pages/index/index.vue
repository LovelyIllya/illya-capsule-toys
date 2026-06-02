<template>
	<view class="content">
		<illyaCapsuleToys :giftImgList="giftImgList" :disabled="disabled" :resLv="resLv" :giftRes="giftRes"
			:resBallImg="resBallImg" @start="start" @canNotStart="canNotStart" @ok="ok" />
	</view>
</template>

<script>
	import illyaCapsuleToys from '../../uni_modules/iliya-capsule-toys/components/illya-capsule-toys/illya-capsule-toys.vue'
	export default {
		components: {
			illyaCapsuleToys
		},
		data() {
			return {
				giftRes: {
					giftName: null,
					url: ""
				},
				giftImgList: [],
				resBallImg: '',
				disabled: false,
				resLv: 1
			}
		},
		onLoad() {

		},
		methods: {
			start(fn) {
				this.giftRes.giftName = '预制菜'
				this.giftRes.url = '../../static/zi-qiu.png'
				fn()
			},
			canNotStart() {
				uni.showModal({
					title: '提示',
					content: '余额不足'
				})
			},
			ok() {
				console.log('确认中奖信息');
			}
		}
	}
</script>

<style>
	.content {
		padding-top: 100rpx;
		background: red;
		height: 100vh;
		box-sizing: border-box;
	}
</style>