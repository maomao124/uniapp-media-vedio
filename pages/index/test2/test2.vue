<template>
	<view>
		<button type="primary" @click="button1">选择视频保存</button>
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
						uni.saveVideoToPhotosAlbum({
							filePath:data.tempFilePath,
							success: (data) => {
								console.log("保存完成");
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