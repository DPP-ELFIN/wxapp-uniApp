<template>
	<view>
		<view class="search" :style="{ 'padding-top': barHeight + 'px' }" @click="handleSearch">
			<view class="search_box">
				<u-icon name="search" color="#ccc" size="28" class="icon"></u-icon>
				<text>搜索</text>
			</view>
			<!-- <u-search placeholder="日照香炉生紫烟" v-model="keyword"></u-search> -->

		</view>
	</view>
</template>

<script>
export default {
	name: "search",
	data() {
		return {
			barHeight: 0
		};
	},
	beforeMount() {
		this.getBarHeight()
	},
	methods: {
		getBarHeight() {
			uni.getSystemInfo({
				success: (res) => {
					this.barHeight = res.statusBarHeight + 6
				}
			})
		},
		handleSearch() {
			uni.navigateTo({
				url: '/subCom-pkg/search/search'
			})
		}
	}
}
</script>

<style scoped lang="scss">
.search {
	width: 100vw;
	position: relative;
	background-color: #fff;
	padding: 0 32rpx 12rpx;
	z-index: 999;
	color: #ccc;

	.search_box {
		position: relative;
		width: 50vw;
		background-color: #f3f3f3;
		height: 64rpx;
		border-radius: 32rpx;
		line-height: 64rpx;
		columns: #ccc;
		font-size: 26rpx;
		padding-left: 20rpx;
		display: flex;
		justify-content: left;
		align-items: center;

		.icon {
			margin-right: 40rpx;
		}
	}
}
</style>