<template>
	<view>
		<button type="primary" @click="button1">选择视频查看信息</button>
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
						uni.getVideoInfo({
							src:data.tempFilePath,
							success: (data) => {
								console.log("视频信息：",data);
							},
							fail: (err) => {
								console.log("错误：",err);
							}
						})
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