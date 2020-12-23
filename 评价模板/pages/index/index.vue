<template>
	<view class="content">
		<my-issue key="1" />
		<my-issue key="2" :score="3" />
		<my-issue key="3" :starsDisabled="true" />
	</view>
</template>

<script>
  import myIssue from '@/components/myIssue.vue'
	export default {
		components:{myIssue},
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content{
		height: 100%;
	}
</style>
