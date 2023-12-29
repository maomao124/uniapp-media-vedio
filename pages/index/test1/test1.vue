<template>
	<view>
		<button type="primary" @click="button1">选择视频</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			button1() {
				uni.chooseVideo({
					success: (data) => {
						console.log(data.tempFilePath);
					},
					fail: (err) => {
						console.log("错误：", err);
					}
				})
			}
		}
	}
</script>

<style>

</style>