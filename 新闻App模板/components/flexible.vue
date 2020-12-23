<template>
	<!-- #ifdef APP-NVUE -->
	<view class="uni-flexible">
		<slot />
		<view class="flexible-line" @appear="handleAppear" @disappear="handleDisappear"></view>
	</view>
	<!-- #endif -->
	<!-- #ifndef APP-NVUE -->
	<view>
		<slot />
		<view class="flexible-line"></view>
	</view>
	<!-- #endif -->
</template>

<script>
	export default {
		name: 'UniFlexible',
		props: {},
		data() {
			return {}
		},
		mounted() {
		},
		methods: {
			createObserver(e) {
				observer = uni.createIntersectionObserver(this);
				observer.relativeTo('.scroll-view').observe('.flexible-line', (res) => {
				})
			},
			handleAppear(e) {
				//console.log(e);
				this.$emit("flexible1", e);
			},
			handleDisappear(e) {
				//console.log(e);
				this.$emit("flexible0", e);
			}
		}
	}
</script>

<style>
	.uni-flexible {
		position: relative;
	}

	.flexible-line {
		position: absolute;
		left: 0;
		right: 0;
		bottom: 2px;
		height: 1px;
	}
</style>
